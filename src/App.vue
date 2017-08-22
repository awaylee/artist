<template>
  <div id="app">
    <v-home></v-home>
    <div class="header">
       header
    </div>
    <div class="content">
      content
    </div>
    <img src="./assets/logo.png">
    <router-view></router-view>
  </div>
</template>

<script>
import home from './components/home/home.vue';

export default {
  name: 'app',
  components:{
    'v-home':home
  }
}
</script>

<style>
#app {
  /*font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;*/
}
</style>
