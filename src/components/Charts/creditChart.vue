<template>
  <div class="small">
    <line-chart :chart-data="datacollection"></line-chart>
    <h3>Credit Chart</h3>
  </div>
</template>

<script>
  import LineChart from './CreditChart.js';
  import axios from 'axios';

  export default {
    components: {
      LineChart
    },
    data () {
      return {
        datacollection: null,
        chartValues:""
      }
    },

    mounted () {

      axios.get("http://13.126.66.83:3000/dashboard-data")
      .then(response=>{
        return(
          this.chartValues=response.data.body.data.creditChart,
          this.fillData()
          )
        })      
    },

    methods: {
      fillData () {
        var keys=[];
        for(var k in this.chartValues) keys.push(k);

        var keyData=[];
        for(var k in keys) keyData.push(this.chartValues[keys[k]]); 

        var color=[];
        for(var k in keys) color.push(this.getRandomColor());  

        this.datacollection = {
          labels: keys,
          datasets: [
            {
              label: ['1','2'],
              backgroundColor: color,
              data:keyData
            }
          ]
        }
      },

      getRandomColor() {
        var letters = '0123456789ABCDEF';
        var color = '#';
        for (var i = 0; i < 8; i++) {
          color += letters[Math.floor(Math.random() * 16)];
        }
        return color; 
      }
    } 
  }
</script>

<style scoped>
  .small {
    width: 300px;
    margin:15px auto;
    padding:0 100px;
    background-color:#fff;
  }
</style>