<template>
	<div class="sectionbody container-fluid">
	   	<div class="justify-content-md-around row no-gutter">
	   		<div class="col-md-7 accountInfo py-4 my-2">
	   			<p class="mainHeading">Account Information</p>
	   			<div class="AmountType py-3">
	   				<div>
	   					<p class="header my-0">Amount Commited</p>
	   					<p class="price my-0"><i class="fas fa-rupee-sign"></i>{{amountCommited}} <i class="decrement fas fa-caret-down"></i></p>
   					</div>
   					<div>
	   					<p class="header my-0">Amount Disbursed</p>
	   					<p class="price my-0"><i class="fas fa-rupee-sign"></i>{{amountDisbursed}} <i class="increment fas fa-caret-up"></i></p>
   					</div>
   					<div>
	   					<p class="header my-0">Amount To Invest</p>
	   					<p class="price my-0"><i class="fas fa-rupee-sign"></i>{{amountToInvest}} <i class="decrement fas fa-caret-down"></i></p>
   					</div>
	   			</div>

				<div class="remainingAmt py-3 mb-4 row">
					<div class="col-md-6">
						<p class="mb-0 header">Remaining Amount</p>
						<h4 class="price" id="fontStyle"><i class="fas fa-rupee-sign"></i>{{remainingAmount}}</h4>
					</div>
					<div class="col-md-5 ml-0"><button class="mt-2 update">Update balance <i class="fas fa-pen"></i></button></div>

				</div>


				<a class="history" href="#">Transaction history  <i class="fas fa-long-arrow-alt-right"></i></a>
	   		</div>

	   		<div class="accountInfo col-md-4 py-4 my-2 ">
				<p class="chartHeading ">Credit Health Report</p>

	   			<CreditChart/>
   			</div>
	   	</div>

	</div>

</template>

<script>
	import CreditChart from '../Charts/creditChart.vue'
	import axios from 'axios'
	

	export default {
	  	components:{
	  		CreditChart
	  	},
	  	data(){
	  		return{
	  			amountToInvest:"",
  		        amountDisbursed:"",
  		        amountCommited:"",
  		        remainingAmount:""
	  		}
	  	},
  	
  		mounted(){
  			axios.get('http://13.126.66.83:3000/dashboard-data')
  			.then(resp=>{
  				return(
  					this.responseData=resp.data.body.data,
  					this.amountToInvest=this.responseData.amountToInvest,
  					this.amountCommited =this.responseData.amountCommitted,
  					this.amountDisbursed=this.responseData.amountDisbursed,
  					this.remainingAmount=this.responseData.remainingAmount
  				)
			})
  		}
    }

</script>

<style scoped>
	
	.chartHeading{
    	color:"#1f3445";
    	font-family: "Helvetica Header",Blippo,fantasy;
    	font-size:16px;
    	margin:20px 5px;
  }
	.accountInfo{
		box-shadow: 0px 0px 5px 1px #495d70;
		border-radius:2px;
	}

	.AmountType div{
		display:inline-block;
		padding:10px 35px 10px 0;
	}

	.update{
		background-color:white;
		border:1px solid #00968b;
		color:#00968b;
		font-weight:200;
		line-height:1.6;
		border-radius:5px;
	}

	.update:hover{
		box-shadow:0px 0px 2px #495d70;
	}

	.header{
		color:#43c7bb;
		font-size:12px;
	}

	.price{
		color:#1f3445;
		font-weight:750;
		font-size:18px;
	}
	
	#fontStyle{
		font-size:24px;
	}

	.history{
		text-decoration:none;
		background-image:linear-gradient(to right,#b0bec5,#eeeeee);
		padding:8px 8px 8px 10px;
		border-radius:5px;
		color:#000d1e;
		box-shadow: 0px 0px 3px #495d70;
	}

	.history:hover{
		box-shadow:0px 0px 4px #b0bec5;
	}

	.decrement{
		color:red;
	}

	.increment{
		color:green;
	}

	.mainHeading{
		color:"#1f3445";
		font-family: "Helvetica Header",Blippo,fantasy;
	}
</style>

