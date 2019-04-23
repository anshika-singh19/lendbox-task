<template>
  <div>
	<div class="sectionbody">
		<EmiGraph class="graph"/>
		<div>
			<InterestData class="boxData"/>
			<InterestData class="boxData"/>
			<InterestData class="boxData"/>
		</div>
	</div>

  </div>
</template>

<script>
	import EmiGraph from '../EmiGraph/emiGraph.vue'
	import InterestData from './InterestData/interestData.vue'

	export default {
		name:'Section2',
	  	components:{
	  		EmiGraph,
	  		InterestData

	  	}
	  
	};
</script>

<style scoped>
	
	.sectionbody{
		display:flex;
	}

	.boxData{
		width:450px;
		height:150px;
		background-color:#b0b1b591;
		margin: 10px 30px;
	}

	
</style>

