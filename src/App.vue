<script lang="ts" setup>

import UserInfo from './components/UserInfo.vue';

</script>

<template>
 <img alt="Vue logo" src="./assets/logo.png">
  <UserInfo/>
</template>



<style lang="scss">
*{
   padding:0 ;
  margin: 0 ;
}
#app {
 
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: lightblue;
  height: 100vh;
  padding-top: 40px;
}

.container{
  width: 90%;
  max-width: 1200px;
  margin: 0px auto;
}
</style>
