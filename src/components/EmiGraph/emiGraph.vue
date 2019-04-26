<template>
  <div class="small">
    <p class="head mt-0">EMI Transaction History</p>
    <line-chart :chart-data="datacollection"></line-chart>
  </div>
</template>

<script>
  import LineChart from './BarChart.js'
  import axios from 'axios'

  export default {
    components: {
      LineChart
    },
    data () {
      return {
        datacollection: null,
        barValues:''
      }
    },
    mounted () {
      axios.get('http://13.126.66.83:3000/dashboard-data')
      .then(response=>{
          return(
            this.barValues=response.data.body.data.graph.emiChartData
            )
      })
      this.fillData()
    },

    methods: {
      fillData () {
        // var keys=[];
        // for(var i=0; i<this.barValues.length; i++) {
        //   for(var k in this.barValues[i]) keys.push(this.barValues[keys[0]]); 

        //   console.log(this.barValues[i])
        //   // keys.push(k.emiDate);
        // }

        // var keyData=[];
        // for(var k in keys) keyData.push(this.barValues[keys[k]]); 
        
          this.datacollection = {
            labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
            datasets: [
              {
                label: 'Data One',
                backgroundColor: '#495d70',
                data: [40, 39, 10, 40, 39, 80, 40]
              }
            ]
          }
        }
      }
    }
  
</script>

<style scoped>
  .small {
    max-width: 300px;
    margin:  0 auto;
    background-color:white;
    padding:0 0 20px 20px;
  }

  .head{
    color:"#1f3445";
    font-size:16px;
    margin-top:10px;
    padding-top:0;
    font-family: "Helvetica Header",Blippo,fantasy;
  }
</style>