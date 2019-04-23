<template>
  <div id="app">
    <NavBar/>
    <Section1/>
    <principleRow/>
    <Section2/>
  </div>
</template>

<script>
  import NavBar from './components/NavBar/NavBar.vue'
  import Section1 from './components/Section1/section1.vue'
  import Section2 from './components/Section2/section2.vue'
  import principleRow from './components/rowSection/principleRow.vue'
  export default {
    components:{
      NavBar,
      Section1,
      Section2,
      principleRow
    }
    
  };
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color:#fbf9fdad;
}
</style>
