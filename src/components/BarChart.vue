<template>
    <div class="h-max-[200px] ">
        <Bar  :data="data" :options="options" />

    </div>
  </template>
  
  <script lang="ts">
  import {
    Chart as ChartJS,
    Title,
    Tooltip,
    Legend,
    BarElement,
    CategoryScale,
    LinearScale
  } from 'chart.js'
  import { Bar } from 'vue-chartjs'
  import * as barConfig from '../chartsConfig/barConfig'
  
  ChartJS.register(CategoryScale, LinearScale, BarElement, Title, Tooltip, Legend)
  
  export default {
    name: 'App',
    components: {
      Bar
    },
    data() {
      return barConfig
    },
    mounted() {
    this.$emit('rendered')
  }
    
  }
  </script>
  