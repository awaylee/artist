<template>
  <div>
    <div class="header">
      <span class="area">北京</span>
      <span class="title">观照自然</span>
      <span class="search">search</span>
    </div>
    <div class="block">
      <el-carousel trigger="click" height="200px">
        <el-carousel-item v-for="item in banner.img">
          <img :src="item" alt="" width="100%">
          <h3>{{ item }}</h3>
        </el-carousel-item>
      </el-carousel>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
import axios from 'axios';

const ERR_OK = 0;

export default{
  data() {
    return {
      banner: []
    }
  },
  created() {
    axios.get('/api/banner').then((response) => {
      response = response.data;
      if (response.errno == ERR_OK) {
        this.banner = response.data;
        console.log('banner:',this.banner);
        this.$nextTick(() => {
          /*this._initScroll();
          this._calculateHeight();*/
        })
      }
    })
    .catch((err) => {
      console.log('error:',err);
    });
  }
}

</script>

<style lang="stylus" rel="stylesheet/stylus">
 .header
   height 40px
   display flex
   line-height 40px
   padding 5px 15px
   background #1F2D3D
   color #fff
   span
     display inline-block
     flex 1
   .search
     text-align right
   .title
      flex 3
      text-align center
 el-carousel__item h3
   color: #475669
   font-size: 14px
   opacity: 0.75
   line-height: 150px
   margin: 0


 .el-carousel__item:nth-child(2n)
   background-color: #99a9bf


 .el-carousel__item:nth-child(2n+1)
   background-color: #d3dce6

</style>