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
          { x: 'Apr', y: 13.5, fill: '#81e2a1', text: 'April' }, 
          { x: 'Jan', y: 3, fill: '#498fff', text:'January' }, 
          { x: 'Feb', y: 3.5, fill: '#ffa060', text: 'February' },
          { x: 'Mar', y: 7, fill: '#ff68b6', text: 'March' }, 
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
  }
};
</script>

