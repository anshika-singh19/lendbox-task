<template>
  <div>
	<div class="sectionbody">
		<Amount class="boxData"/>
		<Amount class="boxData"/>
		<Amount class="boxData"/>
		<Amount class="boxData"/>
	</div>

  </div>
</template>

<script>
	import Amount from '../Amount/amount.vue'
	export default {
		name:'Section2',
	  	components:{
	  		Amount

	  	}
	  
	};
</script>

<style scoped>
	
	.sectionbody{
		display:flex;
		flex-flow:row;
		width:100%;
		padding-left:5px;
	}

	.boxData{
		width:277px;
		height:100px;
		background-image:linear-gradient(to bottom,#93d287,#87d2b6);
		margin: 5px 15px;
		padding-bottom:10px;
	}

</style>

