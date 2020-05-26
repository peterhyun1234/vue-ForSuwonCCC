<template>
  <v-app id="inspire">
    <v-container grid-list-xl>
      <ejs-accumulationchart id="container" :legendSettings='legendSettings' :tooltip='tooltip'>
          <e-accumulation-series-collection>
              <e-accumulation-series 
              :dataSource='seriesData' 
              xName='x' yName='y'
              :radius='radius'
              :border='border'
              :dataLabel='datalabel'
              :pointColorMapping=' pointColorMapping'> </e-accumulation-series>
          </e-accumulation-series-collection>
      </ejs-accumulationchart>
      <v-list three-line subheader>
        <v-subheader>사랑의 언어 테스트 결과</v-subheader>
        <v-list-item >
          <v-list-item-action>
            <v-avatar 
              color="#F5F5F5" 
              size="50"
              >
              <v-icon 
                :color="seriesData[0].fill"
                > {{ seriesData[0].icon }}</v-icon>
            </v-avatar>
          </v-list-item-action>

          <v-card
            class="mx-auto"
            max-width="900"
            outlined
          >
            <v-list-item three-line>
              <v-list-item-content>
                <div class="body-2 mb-2">사랑의 언어 1: </div>
                <v-list-item-title class="headline mb-3">
                  <v-card 
                    class="pt-1 pb-1"
                    style="text-align: center;" 
                    max-width="200" 
                    :color="seriesData[0].fill">
                    <v-card
                      class="ml-6 mr-6"
                      style="opacity: 0.7"
                      max-width="150"
                      outlined
                      color="white">
                      {{ seriesData[0].x }}
                    </v-card>
                  </v-card>
                </v-list-item-title>
                <v-list-item-action-text class="body-2">{{ seriesData[0].simpleDescription }}</v-list-item-action-text>
              </v-list-item-content>
            </v-list-item>

           <v-card-actions>
              <v-expansion-panels
                flat Popout>
                <v-expansion-panel>
                  <v-expansion-panel-header class="body-1 text--secondary">
                    더 보기
                    <template v-slot:actions>
                      <v-icon color="primary">$expand</v-icon>
                    </template>
                  </v-expansion-panel-header>
                  <v-expansion-panel-content>
                    {{seriesData[0].description }}
                  </v-expansion-panel-content>
                </v-expansion-panel>
              </v-expansion-panels>
            </v-card-actions>
          </v-card> 
        </v-list-item>
        <v-list-item >
          <v-list-item-action>
            <v-avatar 
              color="#F5F5F5" 
              size="50"
              >
              <v-icon 
                :color="seriesData[1].fill"
                > {{ seriesData[1].icon }}</v-icon>
            </v-avatar>
          </v-list-item-action>

          <v-card
            class="mx-auto"
            max-width="900"
            outlined
          >
            <v-list-item three-line>
              <v-list-item-content>
                <div class="body-2 mb-2">사랑의 언어 2: </div>
                <v-list-item-title class="headline mb-3">
                  <v-card 
                    class="pt-1 pb-1"
                    style="text-align: center;" 
                    max-width="200" 
                    :color="seriesData[1].fill">
                    <v-card
                      class="ml-6 mr-6"
                      style="opacity: 0.7"
                      max-width="150"
                      outlined
                      color="white">
                      {{ seriesData[1].x }}
                    </v-card>
                  </v-card>
                </v-list-item-title>
                <v-list-item-action-text class="body-2">{{ seriesData[1].simpleDescription }}</v-list-item-action-text>
              </v-list-item-content>
            </v-list-item>

           <v-card-actions>
              <v-expansion-panels
                flat Popout>
                <v-expansion-panel>
                  <v-expansion-panel-header class="body-1 text--secondary">
                    더 보기
                    <template v-slot:actions>
                      <v-icon color="primary">$expand</v-icon>
                    </template>
                  </v-expansion-panel-header>
                  <v-expansion-panel-content>
                    {{seriesData[1].description }}
                  </v-expansion-panel-content>
                </v-expansion-panel>
              </v-expansion-panels>
            </v-card-actions>
          </v-card> 
        </v-list-item>
        <v-list-item>
          <v-list-item-action>
            <v-avatar 
              color="#F5F5F5" 
              size="50"
              >
              <v-icon 
                :color="seriesData[1].fill"
                > {{ seriesData[1].icon }}</v-icon>
            </v-avatar>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title class="mt-3">
              <span>사랑의 언어 2: </span>
              <span class="title">{{ seriesData[1].x }}</span>
            </v-list-item-title>
            <v-list-item-action-text class="subtitle-2 mt-3">{{ seriesData[1].simpleDescription }}</v-list-item-action-text>
            <v-expansion-panels
              flat>
              <v-expansion-panel>
                <v-expansion-panel-header class="body-1 text--secondary">
                  더 보기
                  <template v-slot:actions>
                    <v-icon color="primary">$expand</v-icon>
                  </template>
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  {{seriesData[1].description }}
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
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
          { x: '인정하는 말', y: 1, fill: '#81C784', text: 'A', r: '120', 
            percentage: "",
            icon: 'mdi-podcast', 
            simpleDescription: "인정하는 말이 주언어인 사람은 사랑을 표현하는 방법이 격려의 말, 인정해 주는 말입니다.", 
            description: "칭찬하는 말이나 감사의 표현, 그 사람을 인정하고 높혀주는 말들이 이 사람에겐 행복이고, 큰 힘을 줍니다. 또한 이 사람은 사랑의 감정을 말로 전달하고 싶어하며 온화한 말투를 좋아하고, 명령하는 말투를 극히 싫어합니다. \"미안해 , 고마워, 정말 잘하는구나, 사랑해, 넌 정말 좋은 사람이야\" 와 같은 사과, 칭찬, 격려, 애정의 말들을 배우자, 또는 주변사람들로 부터 들었을때 \"내가 사랑받고 있구나\" 라고 느끼며 매사에 최선을 다하게 됩니다."}, 
          { x: '함께하는 시간', y: 1, fill: '#AED581', text: 'B', r: '120', 
            percentage: "",
            icon: 'mdi-human-male-female', 
            simpleDescription: "함께하는 시간이 주언어인 사람들은 누군가가 자신에게 온전히 관심을 집중시키고 있을때 사랑을 느낍니다.", 
            description: "단순히 상대방과 함께있는걸 좋아하는 것이 아니라, 함께하는 활동 속에서 상대방이 온전히 나에게 집중하고, 관심을 기울여 주기를 원합니다. 함께 외식을 하거나 영화구경을 하면서 서로의 관심 을 나누고, 그 사람의 눈을 마주보며 이야기를 경청해준다면 그 사람을 분명 당신의 사랑을 느낄 수 있을것입니다."}, 
          { x: '선물', y: 1, fill: '#DCE775', text: 'C', r: '120', 
            icon: 'mdi-gift-outline', 
            simpleDescription: "선물이 주언어인 선물이 사람들은 선물이 사랑을 표현하는 수단이라 생각하며 사랑을 나타내는 상징이라 믿습니다.", 
            description: "어떤 사람들은 아름다운 보석이나, 값비싼 물건을 선물해야만 사랑이 전달된다고 믿습니다. 하지만 이 사람들에겐 아주 작은 선물이라도 사랑이 전달되기엔 충분합니다. 주는 사람의 마음만 듬뿍 담겨 있다면 선물의 크고 작음에는 전혀 관계가 없습니다. 당신이 전하는 사랑이 듬뿍 담긴 작은 쪽지 하나라도 이 사람들에겐 평생 간직해고픈 큰 선물일 것입니다." },
          { x: '봉사의 손길', y: 1, fill: '#FFF176', text: 'D', r: '120', 
            percentage: "",
            icon: 'mdi-hand-heart', 
            simpleDescription: "봉사의 손길을 주언어로 가진 사람들은 상대방이 자신을 도와줄때 행복을 느낍니다.", 
            description: "누군가 자신을 위해 무언가를 해줄때 그 속에서 사랑을 느낍니다. 자신의 입으로 원하는 것을 말하기 전에 나를 위해 계획을 세우고 시간을 내서 노력해주길 원합니다. 설겆이, 청소 도와주기, 무거운 물건 대신 들어주기, 등등 누군가 자신을 위해 봉사의 손길을 내민다면 이 사람을 분명히 사랑을 느낄 것입니다." }, 
          { x: '스킨쉽', y: 1, fill: '#FFB74D', text: 'E', r: '120', 
            percentage: "",
            icon: 'mdi-heart-box-outline', 
            simpleDescription: "스킨쉽이 주언어인 사람들은 말그대로 상대방과의 신체접촉을 통해서 행복을 느낍니다.", 
            description: "이 사람들은 힘들때 누군가 손을 잡아 주거나 어깨를 한번 두드려주는 것만으로도 아주 큰 힘이 얻습니다. 상대방이 손으로 머리를 쓰다듬고 사랑을 듬뽁담아 안아준다면 \"난 혼자가 아니야\", \"행복하다\"란 사랑의 감정을 느끼게 될 것입니다." }, 
      ],
      radius: 'r',
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

      this.seriesData[0].percentage = (((parsedResult.A)/30)*100).toFixed(1) + "%"
      this.seriesData[1].percentage = (((parsedResult.B)/30)*100).toFixed(1) + "%"
      this.seriesData[2].percentage = (((parsedResult.C)/30)*100).toFixed(1) + "%"
      this.seriesData[3].percentage = (((parsedResult.D)/30)*100).toFixed(1) + "%"
      this.seriesData[4].percentage = (((parsedResult.E)/30)*100).toFixed(1) + "%"


      // sorting based on y value
      this.seriesData.sort(function(a, b){
        return b.y - a.y;
      })

      this.seriesData[0].r = "130";
      this.seriesData[1].r = "125";

    },
  }
};
</script>

