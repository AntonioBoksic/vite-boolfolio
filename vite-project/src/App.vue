<template>
  <HeaderComp/>

  <!-- <AppHome/> -->
  
  <router-view/>

</template>

<script>
 //import AppHome from './pages/AppHome.vue';
 import HeaderComp from './components/HeaderComp.vue';

 export default {
  name : 'App',
  components : {
    //AppHome
    HeaderComp
  },
 }
</script>

