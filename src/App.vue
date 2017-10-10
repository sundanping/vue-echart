<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style lang="scss">
*{
  box-sizing: border-box;
}
html{
  height: 100%;
  overflow: hidden;
}
body{
  margin: 0;
  font-family: "Helvetica Neue", Helvetica, Arial, "Hiragino Sans GB", "Hiragino Sans GB W3", "Microsoft YaHei UI", "Microsoft YaHei", "WenQuanYi Micro Hei", sans-serif;
  align-content: space-between;
  background-image: url(assets/bg.jpg);
  height: 100%;
  overflow-y: scroll;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100%;
  height: 100%;
  min-width: 959px;
  min-height: 768px;
  padding: 13px;
}
main{
  margin: auto;
}
a{
  text-decoration: none;
}
ul,li{
  margin: 0;
  padding: 0;
}
li{
  list-style: none;
}
</style>
