<template>
    <div class="h-[200px] ">
        <Doughnut :data="data" :options="options" />

    </div>
  </template>
  
  <script lang="ts">
  import { Chart as ChartJS, ArcElement, Tooltip, Legend } from 'chart.js'
  import { Doughnut } from 'vue-chartjs'
  import * as donutsConfig from '../chartsConfig/donutsConfig'
  
  ChartJS.register(ArcElement, Tooltip, Legend)
  
  export default {
    name: 'DonutsChart',
    components: {
      Doughnut
    },
    data() {
      return donutsConfig
    },
    mounted() {
    this.$emit('rendered')
  }
  }
  </script>
  