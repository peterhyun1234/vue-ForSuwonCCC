<template>
  <v-app id="inspire">
    <v-container grid-list-xl>
        <ejs-accumulationchart id="container">
            <e-accumulation-series-collection>
                <e-accumulation-series :dataSource='seriesData' xName='x' yName='y' :border='border'  :dataLabel='datalabel' :pointColorMapping=' pointColorMapping'> </e-accumulation-series>
            </e-accumulation-series-collection>
        </ejs-accumulationchart>
    </v-container>
  </v-app>
</template>

<script>
import Vue from "vue";
import { AccumulationChartPlugin, PieSeries, AccumulationDataLabel } from "@syncfusion/ej2-vue-charts";

Vue.use(AccumulationChartPlugin);

export default {
  data() {
    return {
      seriesData: [
                { x: 'Apr', y: 13.5, fill: '#81e2a1', text: 'April' }, 
                { x: 'Jan', y: 3, fill: '#498fff', text:'January' }, 
                { x: 'Feb', y: 3.5, fill: '#ffa060', text: 'February' },
                { x: 'Mar', y: 7, fill: '#ff68b6', text: 'March' }, 
            ],
            border: {color: 'white', width: 2},
            datalabel: {
              visible: true, 
              name: 'text', },
            pointColorMapping: 'fill',
        };
  },
  provide: {
     accumulationchart: [PieSeries, AccumulationDataLabel]
  }
};
</script>

