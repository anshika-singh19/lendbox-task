<template>
  <div class="">
  	<div class="side-bar pt-2 primary-bg-color normal-screen">
	  	<p class="name pl-4 mb-2">Jane Doe<i class="secondary-color-dark p-2 fas fa-check-circle" v-b-tooltip.hover title='Gold Member'></i></p>
	  	
	  	<div class='pl-4 personal-details'>
	  		<p class='m-0'>Jane.doe@xyz.com</p>
	  		<p class='m-0 mb-2'>+91 xxxxxxxxxx</p>
	  		<a href="#">View profile  >></a>
	  	</div>

	  	<ul class="nav-links my-4 pl-0 h-100">
	  		<li class="pl-4" id="active"><a href="#"><i class="secondary-color-dark pr-2 fas fa-chart-pie"></i>Dashboard</a></li>
	  		<li class="pl-4"><a href="#"><i class="secondary-color-dark pr-2 fas fa-exchange-alt"></i>Transactions</a></li>
	  		<li class="pl-4"><a href="#"><i class="secondary-color-dark pr-2 fas fa-sliders-h"></i>Activities</a></li>
	  		<li class="pl-4"><a href="#"><i class="secondary-color-dark pr-2 fas fa-cog"></i>Settings</a></li>
	  	</ul>
  	</div>

  	<div class="small-screen nav-links pt-2 primary-bg-color">
  		<ul class="h-100 pl-0">
  			<li class="pl-4"><a href="#"><i class="secondary-color-dark pr-2 fas fa-bars" @click="toggle"></i></a></li>
  			<li class="pl-4" id="active"><a href="#"><i class="secondary-color-dark pr-2 fas fa-chart-pie" ></i></a></li>
  			<li class="pl-4"><a href="#"><i class="secondary-color-dark pr-2 fas fa-wallet"></i></a></li>
  			<li class="pl-4"><a href="#"><i class="secondary-color-dark pr-2 fas fa-sliders-h"></i></a></li>
  			<li class="pl-4"><a href="#"><i class="secondary-color-dark pr-2 fas fa-cog"></i></a></li>
  		</ul>
  	</div>
  </div>
</template>

<script>

	export default{
		name:'sideBar',
		data(){
			return{
			}
		},

		methods:{
			toggle(){
			}
		}
	}
	
</script>

<style scoped>
	.side-bar{
		padding:10px 0 10px 0;
		width: 18%;
		height:100%;
		position:fixed;
	}
	.nav-links{
		list-style-type:none;
	}

	.nav-links li{
		padding:10px 8px 10px 0;
		list-style-type:none;
	}

	.primary-bg-color{
		color:#ffffff;
		background-color:#000d1e;
	}

	.personal-details {
		font-size:0.8em;
		color:#ffffffad;
	}

	.personal-details a{
		font-size:1em;
		text-decoration:none;
		color:#43c7bb;	
	}

	.personal-details a:hover{
		color:#00968b;
	}

	.secondary-color-dark{
		color:#00968b;
	}

	.name{
		font-size:1.2em;
	}


	.nav-links a{
		color:#ffffffad;
		font-size:1.2em;
		text-decoration:none;
	}


	.nav-links i{
		font-size: 15px;
	}

 	.nav-links li:hover,#active{
 		color:#ffffff;
 		background-color:#1f3344;
		padding:12px;
 	}

 	@media only screen and (max-width: 600px) {
 		.side-bar{
 			padding:10px 0 10px 0;
			width: 55%;
 		}

 		.small-screen{
 			display:block;
 			padding:10px 0 10px 0;
			width: 15%;
			height:100%;
			position:fixed;
 		}

 		.normal-screen{
 			display:none;
 		}
 	}	

 	@media only screen and (max-width: 768px) and (min-width: 700px)  {
 		.side-bar{
 			padding:10px 0 10px 0;
			width: 25%;	
 		}

 	}	

</style>