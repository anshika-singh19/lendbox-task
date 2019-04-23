<template>
  <div class="amtBox">
   	<p class="inv-amount">{{investmentData}}</p>
   	<p class="inv-heading">{{heading}}</p>
  </div>
</template>

<script>
	import axios from 'axios';

	export default {
	  	name: "AmountBox",
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
	.inv-amount{
		font-size:35px;
		color:#fff;
		font-weight:bold;
		margin-bottom:0;
	}

	.inv-heading{
		margin-top:0;
		font-size:15px;
	}

</style>

