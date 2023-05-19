<!-- eslint-disable vue/no-unused-components -->
<!-- eslint-disable vue/no-unused-components -->



<template>
  <div class="main-page">
    <header1 />
    <div class="main">
      <sidebar />
      <bodymain />
      
    </div>
    <div>
      <h1>Camera Recorder</h1>
      <camera-recorder></camera-recorder>
    </div>
  </div>

  
</template>

<script>
import header1 from './components/header1.vue';
import sidebar from './components/sidebar.vue';
import bodymain from './components/bodymain.vue';

import tabChanger from './components/tabChanger.vue';
import camera from './components/camera.vue';




export default {
  name: 'App',
  components: {
    header1,
    
    sidebar,
    bodymain,
    
    // eslint-disable-next-line vue/no-unused-components
    
    
    
    // eslint-disable-next-line vue/no-unused-components
    tabChanger,
    // eslint-disable-next-line vue/no-unused-components
    camera,
    
    
  
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #d6d6d6;
  /* margin-top: 60px; */
}
</style>




