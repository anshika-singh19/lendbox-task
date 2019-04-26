<template>
  <div class="nav-bar fixed-top">
  	<ul class="mb-0">
	  <li><a href="#"><img class="logo" :src="Logo"/></a></li>
	  <li class="balance "><i class="fas fa-wallet pr-2"v-b-tooltip.hover title='Account Balance'></i><span>5,45,000.00</span></li>
	</ul>
  </div>
</template>

<script>
	import Logo from '../../assets/logo.png';

	export default {
		name:'navBar',
		data(){
			return{
				Logo:Logo
			}
		}
	  
	};
</script>

<style scoped>
	ul {
	  list-style-type: none;
	  padding: 0;
	  height:55px;
	  overflow: hidden;
	  background-color: #000d1e;

	}

	.li{
	  list-style-type: none;
	}

	.logo{
		max-width:130px;
		padding:0;
		float:left;
		margin:14px 0 0 24px;
	}

	.nav-bar{
		padding:0;
		margin:0;
	}

	.balance{
		float:right;
		color:#ffffffad;
		margin:13px 24px 0 0;
	}

	.balance span{
		font-size:15px;
	}

	.balance i{
		color:#00968b;
		font-size:20px;

	}


</style>

