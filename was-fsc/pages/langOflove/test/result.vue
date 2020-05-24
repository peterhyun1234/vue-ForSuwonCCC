<template>
  <v-app id="inspire">
    <v-container grid-list-xl>
      <ejs-accumulationchart id="container" :legendSettings='legendSettings' :tooltip='tooltip'>
          <e-accumulation-series-collection>
              <e-accumulation-series 
              :dataSource='seriesData' 
              xName='x' yName='y' 
              :border='border'
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
        position:'Bottom' ,
        alignment:'Center',
        shapeHeight: 25, shapeWidth: 25,
      },
      seriesData: [
          { x: '인정하는 말', y: 1, fill: '#f8ff69', text: 'A', 
            icon: 'mdi-email-send-outline', 
            description: "인간의 가장 큰 욕구중 하나는 누군가로부터 인정받고 싶은 욕구입니다. 잘한 일을 칭찬해보세요! 우리는 잘한 일이 있어도 말없이 넘어가기 쉽습니다. 그러나 구체적으로 칭찬하는 것이 중요합니다."}, 
          { x: '함께하는 시간', y: 1, fill: '#498fff', text: 'B', 
            icon: 'mdi-email-send-outline', 
            description: "함께 하는 시간이란 누군가에게 온전히 관심을 집중시키는 것을 의미합니다. TV를 끄고 소파에 마주 앉아 대화를 하면서 서로에게 관심을 집중하는 것과 같습니다. 산책을 하며 외식을 할 때도 서로 마주 보며 대화를 하는 것이 중요합니다." }, 
          { x: '선물', y: 1, fill: '#ffa060', text: 'C', 
            icon: 'mdi-email-send-outline', 
            description: "선물은 상징일 수 있지만 선물을 준 사람과 그 때의 느낌은 오래오래 기억됩니다. 마음이 중요하다고 생각하여 선물하지 않으면 나중에는 마음까지 멀어질 수 있습니다. 지금 생각나는 소중한 사람들에게 선물을 전달해보세요!" },
          { x: '봉사(헌신)', y: 1, fill: '#69ffb1', text: 'D', 
            icon: 'mdi-email-send-outline', 
            description: "상대를 도와줌으로써 기쁘게 하고 무엇인가를 함으로써 당신의 사랑을 표현하는 것을 말합니다. " }, 
          { x: '스킨쉽', y: 1, fill: '#ff68b6', text: 'E', 
            icon: 'mdi-email-send-outline', 
            description: "육체적인 접촉을 전혀 갖지 않고 지낸 아이들보다 안아주거나 키스를 해 준 아이들이 훨씬 건강하게 자란다고 합니다." }, 
      ],
      border: {color: 'white', width: 2},
      tooltip:{
        enable: true, 
        format: '${series.name} ${point.x} : ${point.y}',
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

      // sorting based on y value
      this.seriesData.sort(function(a, b){
        return b.y - a.y;
      })

    },
  }
};
</script>

