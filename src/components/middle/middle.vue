<template>
<div class="lists">
  <span class="cheek_topRight"></span>
  <span class="cheek_botleft"></span>
  <div class="title">
    <span>资源地图</span>
  </div>
  <div class="contents">
    <div id="myChart" :style="{width: '100%', height: '100%'}"></div>
  </div>
</div>
</template>
<script>
export default {
  name: 'middle',
  mounted () {
    this.drawLine()
  },
  methods: {
    drawLine () {
    }
  }
}
</script>
<style type="text/scss" lang="scss" scoped>
.lists{
  width: 100%;
  height: 100%;
  flex-basis: 100%;
  float: left;
  padding: 5px;
  overflow: hidden;
  .title{
    position: relative;
    display: table;
    font-size: 18px;
    font-weight: 500;
    height: 10%;
    color: #fff;
    text-align: center;
    padding-left: 20px;
    width: 100%;
  }
  .contents{
    height: calc(100% - 12%);
    width: 100%;
    color: #fff;
  }
}
</style>
