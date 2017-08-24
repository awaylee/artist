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
    <v-footer></v-footer>

  </div>
</template>

<script>
import home from './components/home/home.vue';
import footer from './components/footer/footer.vue';

export default {
  data() {
    return {
      value1: null,
      value2: null
    }
  },
  name: 'app',
  components:{
    'v-home':home,
    'v-footer':footer
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
body
  background #f4f4f4



</style>
