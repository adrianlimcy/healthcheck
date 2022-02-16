<template>
  <q-card class="bg-white q-pa-none full-width">
    <q-card-section class="bg-blue-grey-8">
      <div class="row items-center no-wrap">
        <div class="col">
          <div class="text-h6 text-white text-center">Current Digital Transformation Plans</div>
        </div>
      </div>
    </q-card-section>
    <q-card-section>
      <canvas id="bar-chart"></canvas>
    </q-card-section>
  </q-card>
</template>

<script>
import Chart from 'chart.js'
export default {
  data () {
    return {
    }
  },
  mounted () {
    this.createChart('bar-chart')
  },
  methods: {
    createChart (chartId) {
      const ctx = document.getElementById(chartId)
      const myChart = new Chart(ctx, {
        type: 'bar',
        data: {
          labels: [
            'Implementing',
            'Developed a Digital Transformation Strategy',
           'Currently Developing a Digital Transformation Strategy', 
           'Want to Develop a Digital Transformation Strategy',
            'No Plans'],
          datasets: [
            {
              label: 'percentage',
              backgroundColor: ['#ff0000', '#ff0000', '#ff0000', '#ff0000', '#ff0000'],
              data: [23, 40, 31, 6, 1]
            }
          ]
        },
        options: {
          legend: {
            display: false
          },
          title: {
            display: true,
            text: 'Current Digital Transformation Plans'
          }
        }
      })
      return myChart
    }
  }
}
</script>

<style>
</style>