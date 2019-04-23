<template>
  <div>
	<div class="sectionbody">
	   	<div class="amountDetail">
		   	<div class="amountBox">
			   	<AmountBox class="boxData"/>
			   	<AmountBox class="boxData"/>
			   	<AmountBox class="boxData"/>
			</div>
			<div class="amountInvest">
				<p class="inv">{{investmentData}}</p>
   				<p class="invheading">{{heading}}</p>
			</div>
		</div>
		<CreditChart/>	
	</div>

  </div>
</template>

<script>
	import AmountBox from '../Amount/amount.vue'
	import CreditChart from '../Charts/creditChart.vue'
	import axios from 'axios'
	
	export default {
	  	components:{
	  		AmountBox,
	  		CreditChart
	  	},
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
	.amountBox{
		display:flex;
	}
	
	.amountInvest{
		background-image:linear-gradient(to bottom,gray,white);
		width:659px;
		height:140px;
		margin:5px 15px;
		padding-top:20px;
	}

	.sectionbody{
		display:flex;
		padding: 5px;
	}

	.boxData{
		width:200px;
		height:180px;
		background-color:#c3d3cc;
		margin: 15px 15px;
	}

	.inv{
		font-size:35px;
		color:#fff;
		font-weight:bold;
		margin-bottom:0;
	}

	.invheading{
		margin-top:0;
		font-size:15px;
	}
</style>

