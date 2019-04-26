<template>
  <div class="small">
    <line-chart :chart-data="datacollection"></line-chart>
    <div class="text-center credit-info">
      <p class="mb-2 mt-1">You Credit Score is Fair</p>
      <a href="#" class="report">See Complete Report</a>
    </div>
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

        this.datacollection = {
          labels: keys,
          datasets: [
            {
              label: ['1','2'],
              backgroundColor: ['#1f3344','#495d70','#00695c','#009688','#80cbc4','#64ffda','#e0f2f1'],
              data:[2,4,5,6,7,8,9]
            }
          ],

        }
      },
      options:{
        legend:{
            display: true,
            labels: {
               fontColor: 'rgb(255, 99, 132)'
            }
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
    width: 190px;
    margin:auto;
    background-color:#fff;
  }
  .credit-info{
    color:#00968b;
  }

  .credit-info  a{
    text-decoration:none;
  }

  .report {
    text-decoration:none;
    background-image:linear-gradient(to right,#b0bec5,#eeeeee);
    padding:8px 8px 8px 10px;
    border-radius:5px;
    color:#000d1e;
    box-shadow: 0px 0px 3px #495d70;
  }

  .report:hover{
    box-shadow:0px 0px 4px #b0bec5;
  }

 
</style>