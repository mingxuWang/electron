<template>
  <div id="app">
    <el-container>
      <el-header class="main-header"></el-header>
      <el-container>
        <el-aside width="240px" class="main-aside"></el-aside>
        <el-main>
          <router-view></router-view>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
  export default {
    name: 'soda-b-pc'
  }
</script>

<style>
html,
body,
#app,
.el-container {
  height: 100%;
  overflow: hidden;
}
#app .main-header {
  background-color: #ccc;
}
#app .main-aside{
  background-color: #999;
}
</style>
