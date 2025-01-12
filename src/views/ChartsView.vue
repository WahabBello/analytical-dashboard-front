<template>
    <v-container>
      <h1 class="mb-4">Dashboard des Ventes</h1>
  
      <v-row class="mt-4 mb-4">
        <v-col cols="12" md="4">
          <apexchart
            type="line"
            height="200"
            :options="sparkOptions"
            :series="sparkSeries1"
          />
        </v-col>
        <v-col cols="12" md="4">
          <apexchart
            type="bar"
            height="200"
            :options="sparkOptions"
            :series="sparkSeries2"
          />
        </v-col>
        <v-col cols="12" md="4">
          <apexchart
            type="area"
            height="200"
            :options="sparkOptions"
            :series="sparkSeries3"
          />
        </v-col>
      </v-row>
  
      <v-row class="mt-5 mb-4">
        <v-col cols="12" md="6">
          <apexchart
            type="bar"
            height="300"
            :options="barOptions"
            :series="barSeries"
          />
        </v-col>
        <v-col cols="12" md="6">
          <apexchart
            type="donut"
            height="300"
            :options="donutOptions"
            :series="donutSeries"
          />
        </v-col>
      </v-row>
  
      <v-row class="mt-4 mb-4">
        <v-col cols="12" md="6">
          <apexchart
            type="area"
            height="300"
            :options="areaOptions"
            :series="areaSeries"
          />
        </v-col>
        <v-col cols="12" md="6">
          <apexchart
            type="line"
            height="300"
            :options="lineOptions"
            :series="lineSeries"
          />
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import ApexCharts from 'vue3-apexcharts';
  
  export default defineComponent({
    name: 'ChartsPage',
    components: {
      apexchart: ApexCharts,
    },
    data() {
      return {
        sparkOptions: {
          chart: { sparkline: { enabled: true } },
          xaxis: { categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May'] },
        },
        sparkSeries1: [{ data: [10, 20, 30, 40, 50] }],
        sparkSeries2: [{ data: [50, 40, 30, 20, 10] }],
        sparkSeries3: [{ data: [15, 25, 35, 45, 55] }],
  
        barOptions: {
          chart: { id: 'bar-chart' },
          xaxis: { categories: ['Product A', 'Product B', 'Product C'] },
        },
        barSeries: [{ name: 'Sales', data: [30, 40, 45] }],
  
        donutOptions: {
          labels: ['Product A', 'Product B', 'Product C'],
        },
        donutSeries: [44, 55, 13],
  
        areaOptions: {
          chart: { id: 'area-chart' },
          xaxis: { categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May'] },
        },
        areaSeries: [{ name: 'Revenue', data: [10, 20, 30, 40, 50] }],
  
        lineOptions: {
          chart: { id: 'line-chart' },
          xaxis: { categories: ['Week 1', 'Week 2', 'Week 3', 'Week 4'] },
        },
        lineSeries: [{ name: 'Profit', data: [5, 15, 25, 35] }],
      };
    },
  });
  </script>
  
  <style scoped>
  h1 {
    font-family: 'Titillium Web', sans-serif;
    font-weight: 600;
    color: #333;
  }
  </style>
  