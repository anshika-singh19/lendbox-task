<template>
  <div class="mb-5">
   	<p class="head">Loan Details</p>

   	<div class="LoanData">Total Loan to be paid <span class="badge badge-secondary">11</span></div>
   	<div class="LoanData bg-white">Loan already paid <span class="badge badge-secondary">8</span></div>
   	<div class="LoanData">Prepaid loan <span class="badge badge-secondary">12</span></div>
  </div>
</template>

<script>
	import axios from 'axios';

	export default {
	  	name: "interestData",
		data:function(){
	  		return{
	  			heading:" ",
	  			investmentData:" ",
	  			responseData:" "
	  		}
	  	},
  	
  		mounted(){
  			axios.get('http://13.126.66.83:3000/dashboard-data')
  			.then(resp=>{
  				return(
  					this.responseData=resp.data.body.data,
  					this.updateText()
  				)
			})
  		},

  		methods:{
	  		updateText(){
	  			var keys=[];
	  			for(let k in this.responseData) keys.push(k);
	  			this.heading=keys[5];
	  			this.investmentData=this.responseData[keys[5]];
	  		}
	  	}
	}

  	
</script>

<style scoped>
	.head{
		color:"#1f3445";
		font-family: "Helvetica Header",Blippo,fantasy;
	}

	.LoanData{
	background-color:#cfd8dc;
	font-size: 16px;
	padding:20px;

}

</style>

