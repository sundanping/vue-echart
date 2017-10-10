<template>
<div class="lists">
  <span class="cheek_topRight"></span>
  <span class="cheek_botleft"></span>
  <div class="title">
    <span>选题进展</span>
  </div>
  <ul class="nav-box">
    <li class="nav">
      <div class="list_title">选题名称</div>
      <div class="person">执行者</div>
      <div class="time">时间</div>
      <div class="pendReview rev">待审核</div>
      <div class="audited rev">已审核</div>
      <div class="processing rev">进行中</div>
      <div class="completed">已完成</div>
    </li>
    <li class="content" v-for="item in lists">
      <div class="list_title">选题名称选题名称选题名称选题名称选题名称</div>
      <div class="person">执行者</div>
      <div class="time">时间</div>
      <div class="pendReview rev">
        <span class="line"></span>
      </div>
      <div class="audited rev">
        <span class="line"></span>
      </div>
      <div class="processing rev">
        <span class="line"></span>
      </div>
      <div class="completed">
        <span class="line"></span>
      </div>
    </li>
  </ul>
</div>

</template>
<script>
let clue = require('../../json/clue.json')
export default {
  name: 'left',
  data () {
    return {
      lists: clue.data
    }
  },
  created () {
  },
  mounted () {
  },
  computed: {
  },
  methods: {
  },
  watch: {
  }
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
  .nav-box{
    width: 100%;
    height: 87%;
    color: #fff;
    .nav{
      padding: 0 16px;
      background: rgba(7, 99, 243, 0.6);
      height: 10%;
    }
    div{
      float: left;
      height: 100%;
      display: flex;
      align-items: center;
      text-align: center;
    }
    .list_title{
      color: white;
      align-self: center;
      font-size: 14px;
      width: 45%;
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
    }
    .person{
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
      justify-content: center;
      width: 10%;
    }
    .time{
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
      justify-content: center;
      width: 9%;
    }
    .rev{
      width: 9%;
      justify-content: center;
    }
    .completed{
      width: 9%;
      justify-content: center;
    }
  }
  .content{
    height: 14%;
    color: #d6e6ff;
    width: 100%;
    padding: 0 16px;
    background: rgba(139, 170, 219, 0.2);
    font-weight: bold;
    margin-bottom: 3px;
    .line{
      height: 2px;
      background: rgba(132, 132, 132, 0.6);
      width: 25px;
      /*background: #f69420 !important;*/
    }
  }
}
</style>
