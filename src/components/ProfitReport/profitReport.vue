<template>
  <div class="small">
    <line-chart :chart-data="datacollection"></line-chart>
  </div>
</template>

<script>
  import LineChart from './LineBar.js'

  export default {
    components: {
      LineChart
    },
    data () {
      return {
        datacollection: null
      }
    },
    mounted () {
      this.fillData()
    },
    methods: {
      fillData () {
        this.datacollection = {
          labels: [20,40,100,60],
          datasets: [
            {
              label: 'Data One',
              borderColor:'rgba(0,150,139,1)',
              backgroundColor:'rgba(255,255,255,0)',
              data: [20, 70, 80,60],
              fontColor:"#ffffff"

            }
          ]
        }
      },
    }
  }
</script>

<style scoped>
  .small {
    max-width: 300px;
  }
</style>