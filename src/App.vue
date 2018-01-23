<template>
  <div class="convenience-index">
    <el-container>
      <Header class="top"></Header>
      <Menu class="left"></Menu>
      <router-view class="center"></router-view>
    </el-container>
  </div>
</template>

<script>
import Header from './pages/layout/header.vue'
import Menu from './pages/layout/menu.vue'
export default {
  name: 'App',
  components:{
    Header,
    Menu

  },
  data(){
    return {

    }
  }
}
</script>

<style lang="less">
  body{
    padding: 0px;
    margin: 0px;
    .convenience-index{
      width: 100%;
      height: 100%;
      .top{
        position: fixed;
        top: 0px;
        left:0px;
        width: 100%;
        height: 60px;
        z-index: 9999;
      }

      .left{
        position: fixed;
        top: 60px;
        left: 0px;
        width: 200px;
        height: calc(~"100vh - 60px");
      }
      .Goleft{
        -webkit-transform: translateX(-50%);
        -moz-transform: translateX(-50%);
        -ms-transform: translateX(-50%);
        -o-transform: translateX(-50%);
        transform: translateX(-50%);
        -webkit-transition-property: -webkit-transform;
        -moz-transition-property: -moz-transform;
        transition-property: transform;
        -webkit-transition-duration: 0.2s;
        -moz-transition-duration: 0.2s;
        transition-duration: 0.2s;
      }
      .center{
        position: fixed;
        top: 60px;
        left:200px;
        padding: 20px;
        width: 100%;
        height: 100%;

      }


    }
  }

</style>
