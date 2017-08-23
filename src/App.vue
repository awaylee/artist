<template>
  <div id="app">
    <v-home></v-home>
    <div class="content" ref="content">
      <div class="block">
        <span class="demonstration">默认不区分颜色</span>
        <el-rate v-model="value1"></el-rate>
      </div>
      <div class="block">
        <span class="demonstration">区分颜色</span>
        <el-rate
                v-model="value2"
                :colors="['#99A9BF', '#F7BA2A', '#FF9900']">
        </el-rate>
      </div>
    </div>
    <img src="./assets/logo.png">
    <router-view></router-view>
    <div class="footer">

    </div>
  </div>
</template>

<script>
import home from './components/home/home.vue';

export default {
  data() {
    return {
      value1: null,
      value2: null
    }
  },
  name: 'app',
  components:{
    'v-home':home
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">


.footer
  width 100%
  height 60px
  position fixed
  left 0
  bottom 0
  background #2c3e50;

</style>
