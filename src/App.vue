<template>
  <div id="app">
    <NavBar/>
    <div class="d-flex py-5">
      <SideBar/>
          
      <div class="mainSection">
        <p class="heading pt-4 mb-4 pl-3">Finance Report Dashboard</p>
        <Section1/>
        <midSection/>
        <Section2/>
      </div>
    </div>
    <div></div>
  </div>
</template>

<script>
  import NavBar from './components/NavBar/NavBar.vue'
  import SideBar from './components/sideBar/sideBar.vue'
  import Section1 from './components/Section1/section1.vue'
  import midSection from './components/midSection/midSection.vue'
  import Section2 from './components/Section2/section2.vue'

  import Vue from 'vue'
  import BootstrapVue from 'bootstrap-vue'

  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'

  export default {
    components:{
      NavBar,
      SideBar,
      Section1,
      midSection,
      Section2
    }
    
  };
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}


.mainSection{
  position:absolute;
  left:19.5%;
  width:78%;
}

.heading{
    color:#b0bec5;
    font-weight:bold;
    font-size:20px;
    margin-bottom:40px;
}


  @media only screen and (max-width: 600px) {
      .mainSection{
      left:17%;
      width:80%;
    }
  } 

  @media only screen and (max-width: 768px) and (min-width: 700px)  {
    .mainSection{
      left:28%;
      width:82%;
    }

  } 

</style>
