<template>
  <div class="sectionbody container">
	<div class="row justify-content-between">
		<div class="col-lg-5">
			<LoanData/>
		</div>

		<EmiGraph class="graph col-lg-6"/>
		
	</div>

  </div>
</template>

<script>
	import EmiGraph from '../EmiGraph/emiGraph.vue'
	import LoanData from './LoanData/LoanData.vue'

	export default {
		name:'Section2',
	  	components:{
	  		EmiGraph,
	  		LoanData

	  	}
	  
	};
</script>

<style scoped>



	
</style>

