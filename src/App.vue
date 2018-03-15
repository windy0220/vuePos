<template>
  <div id="app">
    <!-- 左侧导航 -->
    <div class="leftbox">
      <leftNav></leftNav>
    </div>

    <!-- 内容区 -->
    <div class="main">
      <router-view></router-view>
    </div>

  </div>
</template>

<script>
import leftNav from "./components/common/leftNav";
export default {
  name: "App",
  components: {
    leftNav
  }
};
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  position: relative;
}
.main {
  position: absolute;
  left: 100px;
  background-color: #eff2f7;
  height: 100%;
  overflow: auto;
}
.leftbox{
  position: absolute;
  left: 0;
  width: 100px;
  height: 100%;
  overflow: auto;
  z-index: 1;
}
</style>
