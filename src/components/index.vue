<template>

<section class="section-box">
  <div class="line">
    <div class="top-left borders paddingRight">
      <top-left></top-left>
    </div>
    <div class="top-middle borders paddingRight">
      <top-middle></top-middle>
    </div>
    <div class="top-right borders">
      <top-right></top-right>
    </div>
  </div>
  <div class="line">
    <div class="middle-left borders paddingRight">
      <middle-left></middle-left>
    </div>
    <div class="middle-middle borders paddingRight">
      <middle-middle></middle-middle>
    </div>
    <div class="middle-right borders">
      <middle-right></middle-right>
    </div>
  </div>
  <div class="line">
    <div class="bot-left borders paddingRight">
      <bot-left></bot-left>
    </div>
    <div class="bot-right">
      <bot-right></bot-right>
    </div>
  </div>
</section>

</template>
<script>
import topLeft from './top/left.vue'
import topMiddle from './top/middle.vue'
import topRight from './top/right.vue'
import middleLeft from './middle/left.vue'
import middleMiddle from './middle/middle.vue'
import middleRight from './middle/right.vue'
import botLeft from './bottom/left.vue'
import botRight from './bottom/right.vue'

export default {
  name: 'index',
  components: {
    topLeft,
    topMiddle,
    topRight,
    middleLeft,
    middleMiddle,
    middleRight,
    botLeft,
    botRight
  }
}
</script>
<style type="text/scss" lang="scss">
.section-box{
  width: 100%;
  height: 100%;
  .line{
    width: 100%;
    height: 33%;
    margin-bottom: 0.33%;
  }
  .borders{
    width: 33.333%;
    height: 100%;
    float: left;
  }
  .paddingRight{
    padding-right: 7px;
  }
  .bot-right{
    width: 66.666%;
    height: 100%;
    float: left;
  }
}
</style>
