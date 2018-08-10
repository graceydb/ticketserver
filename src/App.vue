<template>
  <div id="app">
    <el-container style="height: 100%;">
      <el-aside width="200px" style="background-color: #20222A;">
        <el-menu
                default-active="1-1"
                class="el-menu-vertical-demo"
                background-color="#20222A"
                text-color="#fff"
                active-text-color="#ffd04b">
            <el-menu-item index="1">
                <i class="el-icon-location"></i>
                <router-link to="/movie">
                    影片管理
                </router-link>
            </el-menu-item>
          <el-menu-item index="2">
            <i class="el-icon-document"></i>
            <span slot="title">影院管理</span>
          </el-menu-item>
          <el-menu-item index="3">
            <i class="el-icon-menu"></i>
            <span slot="title">资讯管理</span>
          </el-menu-item>
          <el-menu-item index="4">
            <i class="el-icon-setting"></i>
            <span slot="title">订单管理</span>
          </el-menu-item>
          <el-menu-item index="5">
            <i class="el-icon-setting"></i>
            <span slot="title">用户管理</span>
          </el-menu-item>
        </el-menu>
      </el-aside>
      <el-container>
        <el-header height="60px" style="background-color: #fff;border-bottom: 1px solid #F2F6FC;">
          header
        </el-header>
        <el-main>
          <router-view></router-view>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>

  export default {
      data(){
          return {

          }
      }
  }

</script>

<style>
  html,body{
    height: 100%;
    width: 100%;
    overflow: hidden;
    margin: 0px;
    background-color: #f2f2f2;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    height: 100%;
  }
  .el-menu{
    border-right: 0px !important;
  }
    .router-link-active{
        color: #fff;
        text-decoration: none;
    }
    .block{
        background-color: #fff;
        padding: 10px;
    }
</style>
