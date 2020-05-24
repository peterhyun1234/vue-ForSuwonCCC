<template>
  <v-app id="inspire">
    <v-container grid-list-xl>
      사랑의 언어 테스트 결과
        <ejs-accumulationchart id="container" :legendSettings='legendSettings' :tooltip='tooltip'>
            <e-accumulation-series-collection>
                <e-accumulation-series 
                :dataSource='seriesData' 
                xName='x' yName='y' 
                :border='border'
                :pointColorMapping=' pointColorMapping'> </e-accumulation-series>
            </e-accumulation-series-collection>
        </ejs-accumulationchart>
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
          { x: '인정하는 말', y: 1, fill: '#f8ff69', text: 'A' }, 
          { x: '함께하는 시간', y: 1, fill: '#498fff', text: 'B' }, 
          { x: '선물', y: 1, fill: '#ffa060', text: 'C' },
          { x: '봉사(헌신)', y: 1, fill: '#69ffb1', text: 'D' }, 
          { x: '스킨쉽', y: 1, fill: '#ff68b6', text: 'E' }, 
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
      //console.log(parsedResult);

      this.seriesData[0].y = parsedResult.A;
      this.seriesData[1].y = parsedResult.B;
      this.seriesData[2].y = parsedResult.C;
      this.seriesData[3].y = parsedResult.D;
      this.seriesData[4].y = parsedResult.E;

      // sorting based on y value
      this.seriesData.sort(function(a, b){
        return b.y - a.y;
      })

      console.log(this.seriesData)
    },

  }
};
</script>

