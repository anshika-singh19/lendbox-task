<template>
  <div class="nav-bar">
  	<ul>
	  <li><a href="#">Logo</a></li>
	</ul>
  </div>
</template>

<script>
	
	export default {
		name:'navBar'
	  
	};
</script>

<style>
	ul {
	  list-style-type: none;
	  margin: 0;
	  padding: 0;
	  overflow: hidden;
	  background-color: #5e96c7;
	}

	li {
	  float: left;
	}

	li a {
	  display: block;
	  color: white;
	  text-align: center;
	  padding: 14px 16px;
	  text-decoration: none;
	  font-size:1.5em;
	}
</style>

