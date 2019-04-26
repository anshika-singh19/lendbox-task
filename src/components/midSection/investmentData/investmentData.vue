<template>
  <div class="loanData">
    <p>Investment Record</p>

    <div class="mb-0">Principal Invested</div>
    <div class="progress my-0">
      <div class="progress-bar bg-progress-1" role="progressbar" aria-valuenow="Invested" aria-valuemin="0" aria-valuemax="100"></div>
    </div>
    <h3>85%</h3>
    
    <div class="mb-0">Principal Recieved</div>
    <div class="progress my-0">  
      <div class="progress-bar bg-progress-2" role="progressbar" aria-valuenow="Recieved" aria-valuemin="0" aria-valuemax="100"></div>
    </div>
    <h3>75%</h3>
    
    <div class="mb-0">Outstanding Principal</div>
    <div class="progress my-0">  
      <div class="progress-bar bg-progress-3" role="progressbar" aria-valuenow="Outstanding" aria-valuemin="0" aria-valuemax="100"></div>
    </div>
    <h3>30%</h3>

    <div class="avgInvestment mb-0 py-1">
        <p class="head">Average Investment</p>
        <p class="price">58935.48</p>
    </div>
  </div>
</template>

<script>

  export default {
   name:'loanData',

    data(){
      return{
        Invested:1827000, 
        Recieved:1571231.13, 
        Outstanding:255768.87,
        Average:15
      }
    }

  }
  
</script>

<style scoped>
  .loanData>div{
      margin:30px 25px;
  }

  .bg-progress-1{
    width:80%;
    background-color:#1f3445;
  }

  .bg-progress-2{
    width:75%;
    background-color:#00968b;
  }

  .bg-progress-3{
    width:30%;
    background-color:#43c7bb;
  }

  .loanData h3{
    padding-left:30px;
  }

  .loanData>p{
    padding:10px 0 0 20px;
    font-family: "Helvetica Header",Blippo,fantasy;
  }

  .avgInvestment{
    text-align:center;
    background-color:#cfd8dc;
  }

  .price{
    font-size:27px;
    color:#00968b;
  } 

  .head{
    font-size:13px;
    margin-bottom:0;
  }

  

</style>