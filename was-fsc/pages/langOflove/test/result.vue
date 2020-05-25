<template>
  <v-app id="inspire">
    <v-container grid-list-xl>
      <ejs-accumulationchart id="container" :legendSettings='legendSettings' :tooltip='tooltip'>
          <e-accumulation-series-collection>
              <e-accumulation-series 
              :dataSource='seriesData' 
              xName='x' yName='y' 
              :border='border'
              :dataLabel='datalabel'
              :pointColorMapping=' pointColorMapping'> </e-accumulation-series>
          </e-accumulation-series-collection>
      </ejs-accumulationchart>
      <v-list three-line subheader>
        <v-subheader>사랑의 언어 테스트 결과</v-subheader>
        <v-list-item>
          <v-list-item-action>
            <v-icon>{{ seriesData[0].icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>사랑의 언어 1: {{ seriesData[0].x }}</v-list-item-title>
            <v-list-item-subtitle>{{ seriesData[0].description }}</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-divider></v-divider>
        <v-list-item>
          <v-list-item-action>
            <v-icon>{{ seriesData[1].icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>사랑의 언어 2: {{ seriesData[1].x }}</v-list-item-title>
            <v-list-item-subtitle>{{ seriesData[1].description }}</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-container>
  </v-app>
</template>

<script>
import Vue from "vue";
import { AccumulationChartPlugin, PieSeries, AccumulationDataLabel, AccumulationLegend, AccumulationTooltip } from "@syncfusion/ej2-vue-charts";

Vue.use(AccumulationChartPlugin);

export default {
  data() {
    return {
      legendSettings:{ 
        position:'Top' ,
        alignment:'Center',
        shapeHeight: 25, shapeWidth: 25,
      },
      seriesData: [
          { x: '인정하는 말', y: 1, fill: '#f8ff69', text: 'A', 
            percentage: "",
            icon: 'mdi-email-send-outline', 
            description: "사랑을 표현하는 방법이 격려의 말, 인정해 주는 말입니다. 칭찬하는 말이나 감사의 표현, 그 사람을 인정하고 높혀주는 말들이 이 사람에겐 행복이고, 큰 힘을 줍니다. 또한 이 사람은 사랑의 감정을 말로 전달하고 싶어하며 온화한 말투를 좋아하고, 명령하는 말투를 극히 싫어합니다. \"미안해 , 고마워, 정말 잘하는구나, 사랑해, 넌 정말 좋은 사람이야\" 와 같은 사과, 칭찬, 격려, 애정의 말들을 배우자, 또는 주변사람들로 부터 들었을때 \"내가 사랑받고 있구나\" 라고 느끼며 매사에 최선을 다하게 됩니다."}, 
          { x: '함께하는 시간', y: 1, fill: '#498fff', text: 'B', 
            percentage: "",
            icon: 'mdi-email-send-outline', 
            description: "함께 하는 시간이란 누군가에게 온전히 관심을 집중시키는 것을 의미합니다. TV를 끄고 소파에 마주 앉아 대화를 하면서 서로에게 관심을 집중하는 것과 같습니다. 산책을 하며 외식을 할 때도 서로 마주 보며 대화를 하는 것이 중요합니다." }, 
          { x: '선물', y: 1, fill: '#ffa060', text: 'C', 
            icon: 'mdi-email-send-outline', 
            description: "선물은 상징일 수 있지만 선물을 준 사람과 그 때의 느낌은 오래오래 기억됩니다. 마음이 중요하다고 생각하여 선물하지 않으면 나중에는 마음까지 멀어질 수 있습니다. 지금 생각나는 소중한 사람들에게 선물을 전달해보세요!" },
          { x: '봉사의 손길', y: 1, fill: '#69ffb1', text: 'D', 
            percentage: "",
            icon: 'mdi-email-send-outline', 
            description: "상대를 도와줌으로써 기쁘게 하고 무엇인가를 함으로써 당신의 사랑을 표현하는 것을 말합니다. " }, 
          { x: '스킨쉽', y: 1, fill: '#ff68b6', text: 'E', 
            percentage: "",
            icon: 'mdi-email-send-outline', 
            description: "육체적인 접촉을 전혀 갖지 않고 지낸 아이들보다 안아주거나 키스를 해 준 아이들이 훨씬 건강하게 자란다고 합니다." }, 
      ],
      border: {color: 'white', width: 3},
      tooltip:{
        enable: true, 
        format: '${series.name} ${point.x} : ${point.y}',
      },
      datalabel: {
        visible: true,
        position: 'Inside',
        name: 'percentage',
        font: {color: "white", size: "16px" },
      },
      pointColorMapping: 'fill',
    };
  },
  provide: {
     accumulationchart: [PieSeries, AccumulationDataLabel, AccumulationLegend, AccumulationTooltip]
  },

  created() {
    this.init();
  },

  methods: {
    init () {
      // get data from localstorage
      const result = localStorage.getItem("result");
      const parsedResult = JSON.parse(result);

      this.seriesData[0].y = parsedResult.A;
      this.seriesData[1].y = parsedResult.B;
      this.seriesData[2].y = parsedResult.C;
      this.seriesData[3].y = parsedResult.D;
      this.seriesData[4].y = parsedResult.E;

      //console.log(parsedResult.A + "/" + "30 = " + parsedResult.A/30);

      this.seriesData[0].percentage = (((parsedResult.A)/30)*100).toFixed(2) + "%"
      this.seriesData[1].percentage = (((parsedResult.B)/30)*100).toFixed(2) + "%"
      this.seriesData[2].percentage = (((parsedResult.C)/30)*100).toFixed(2) + "%"
      this.seriesData[3].percentage = (((parsedResult.D)/30)*100).toFixed(2) + "%"
      this.seriesData[4].percentage = (((parsedResult.E)/30)*100).toFixed(2) + "%"


      // sorting based on y value
      this.seriesData.sort(function(a, b){
        return b.y - a.y;
      })

    },
  }
};
</script>

