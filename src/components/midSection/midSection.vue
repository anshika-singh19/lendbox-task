<template>
  <div class="container-fluid midSection">
  	<div class="row justify-content-between">
  		<div class="col-md-6 profit-graph ">
  			<p class="head">Profit Trends</p>
  			<p class="date">April '19</p>
			<profitReport/>
			
			<div class="profitInfo">
				<div class="d-inline-block">
					<p class="heading">Total Profit</p>
					<p class="price"><i class="fas fa-rupee-sign"></i> 23456</p>
				</div>
				<i class="fas fa-long-arrow-alt-up profit"></i>
			</div>

			<div class="profitInfo">
				<div class="d-inline-block">
					<p class="heading">Total Investment</p>
					<p class="price"><i class="fas fa-rupee-sign"></i> 45000</p>
				</div>
				<i class="fas fa-long-arrow-alt-down loss"></i>
			</div>

  		
  		</div>

  		<div class="col-lg-6">
  			<InvestmentData/>
  		</div>
	</div>
  </div>		
</template>

<script>
	import profitReport from '../ProfitReport/profitReport.vue'
	import InvestmentData from './investmentData/investmentData.vue'

	export default {
		name:'midSection',
	  	components:{
	  		profitReport,
	  		InvestmentData
	  	}
	  
	};
</script>

<style scoped>
	.profit-graph{
		padding:10px 10px;
		background-color:#1f3445;
		border-radius:5px;
		box-shadow:0 0 5px #00000;
		
	}	

	.head{
		color:#ffffff;
		padding:20px 0 0 20px;
		font-family: "Helvetica Header",Blippo,fantasy;
	}

	.date{
		color:#ffffff;
		text-align:center;
		border:1px solid #ffffff;
		font-weight:bold;
		width:100px;
		font-family: "Avenir", Helvetica, Arial, sans-serif;
		font-size:12px;
		border-radius:4px;
		padding:3px;
		margin:0 auto;

	}

	.midSection{
		margin:60px 0;
		padding:0 35px;
	}		

	.profitInfo{
		background-color:#ffffff;
		border-radius:4px;
		margin:15px 4px;
		padding:2px 10px;
		display:inline-block;
	}

	.profitInfo:last-of-type{
		float:right;

	}

	.profitInfo:first-of-type{
		float:left;

	}

	.heading, .price{
		padding:0;
		margin:0;
	}

	.price{
		color:#000d1e;
		text-align:center;
		font-size:20px;
	}
	.profitInfo>i{
		font-size:45px;
		margin:5px;
	}

	.heading{
		font-size:10px;
	}

	.profit{
		color:green;
	}

	.loss{
		color:red;
	}

	@media only screen and (max-width: 600px){
		.profitInfo{
			display:block;
			text-align:center;
		}

		.profitInfo:last-of-type{
			float:none;
		}
	}

</style>

