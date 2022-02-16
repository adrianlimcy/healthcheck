<template>
  <q-card class="bg-white q-pa-none full-width">
    <q-card-section class="bg-blue-grey-8">
      <div class="row items-center no-wrap">
        <div class="col">
          <div class="text-h6 text-white text-center">Strength of Digital Backbone</div>
        </div>
      </div>
    </q-card-section>
    <q-card-section>
      <canvas id="digiBack-chart"></canvas>
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
    this.createChart('digiBack-chart')
  },
  methods: {
    createChart (chartId) {
      const ctx = document.getElementById(chartId)
      const myChart = new Chart(ctx, {
        type: 'bar',
        data: {
          labels: [
            'Excellent',
            'Very Good',
            'Fair',
            'Poor'],
          datasets: [
            {
              label: 'percentage',
              backgroundColor: ['#ff0000', '#ff0000', '#ff0000', '#ff0000'],
              data: [20, 42, 33, 5]
            }
          ]
        },
        options: {
          legend: {
            display: false
          },
          title: {
            display: true,
            text: 'Strength of Digital Backbones'
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