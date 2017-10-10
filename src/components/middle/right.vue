<template>
<div class="lists">
  <span class="cheek_topRight"></span>
  <span class="cheek_botleft"></span>
  <div class="title">
    <span>新媒体运营</span>
  </div>
  <ul class="contents-box">
    <li class="top">
      <div class="top-title">
        <div class="titles">累计APP下载次数</div>
        <div class="frequency">启动次数</div>
        <div class="frequency">注册用户</div>
        <div class="frequency">活跃次数</div>
      </div>
      <div class="bot-content">
        <div class="titles"></div>
        <div class="frequency">22089</div>
        <div class="frequency">4260</div>
        <div class="frequency">17791</div>
      </div>
    </li>
    <li class="top">
      <div class="top-title">
        <div class="titles">累计网站访问量</div>
        <div class="frequency">uv</div>
        <div class="frequency">IP</div>
        <div class="frequency">活跃用户</div>
      </div>
      <div class="bot-content">
        <div class="titles"></div>
        <div class="frequency">22089</div>
        <div class="frequency">4260</div>
        <div class="frequency">17791</div>
      </div>
    </li>
    <li class="top">
      <div class="top-title">
        <div class="titles">累计微信粉丝总数</div>
        <div class="frequency">阅读次数</div>
        <div class="frequency">关注人数</div>
        <div class="frequency">消息数</div>
      </div>
      <div class="bot-content">
        <div class="titles"></div>
        <div class="frequency">22089</div>
        <div class="frequency">4260</div>
        <div class="frequency">17791</div>
      </div>
    </li>
  </ul>
</div>
</template>
<script>
  export default {
    name: 'right'

  }
</script>
<style type="text/scss" lang="scss" scoped>
.lists{
  width: 100%;
  height: 100%;
  flex-basis: 100%;
  float: left;
  border: 1px solid #72a4f2;
  padding: 5px;
  background: rgba(16, 43, 85, 0.6);
  position: relative;
  .cheek_topRight{
    display: inline-block;
    position: absolute;
    width: 16px;
    height: 16px;
    top: 0;
    right: 0;
    border-top: 1px solid #72a4f2;
    border-right: 1px solid #72a4f2;
  }
  .cheek_botleft{
    display: inline-block;
    position: absolute;
    width: 16px;
    height: 16px;
    bottom: 0;
    left: 0;
    border-bottom: 1px solid #72a4f2;
    border-left: 1px solid #72a4f2;
  }
  .title{
    position: relative;
    margin-bottom: 1%;
    display: table;
    font-size: 18px;
    font-weight: 500;
    height: 12%;
    color: #fff;
    text-align: center;
    padding-left: 20px;
  }
  .contents-box{
    width: 100%;
    height: 88%;
  }
  .top{
    width: 100%;
    height: 32.333%;
    margin-bottom: 1%;
    background: rgba(47, 82, 143, 0.3);
    .top-title{
      height: 45%;
      padding: 0 5px;
      margin-bottom: 2px;
    }
    .bot-content{
      height: 50%;
      width: 100%;
    }
    .titles{
      height: 100%;
      width: 55%;
      float: left;
      display: flex;
      align-items: center;
      font-weight: bold;
      color: #fff;
      font-size: 16px;
    }
    .frequency{
      width: 15%;
      float: left;
      height: 100%;
      display: flex;
      align-items: center;
      font-weight: bold;
      color: #fff;
      font-size: 16px;
    }
  }
}
</style>
