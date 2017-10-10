<template>
<div class="lists">
  <span class="cheek_topRight"></span>
  <span class="cheek_botleft"></span>
  <div class="title">
    <span>线索汇聚</span>
  </div>
  <nav class="nav-box">
    <div class="nav-list" v-for="nav in nav">
      {{nav.name}}
    </div>
  </nav>
  <ul class="content-box">
    <li class="content" v-for="item in lists">
      <div class="text">
        {{item.title}}
      </div>
      <div class="data">
        <span>百度新闻</span>
        <span>09-17</span>
      </div>
    </li>
  </ul>
</div>

</template>
<script>
let clue = require('../../json/clue.json')
export default {
  name: 'topLeft',
  data () {
    return {
      nav: [{name: '互联网'}, {name: '微信'}],
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
    height: 10%;
    color: #fff;
    .nav-list{
      display: table;
      float: left;
      padding: 0 5px;
      background-color: rgba(139, 170, 219, 0.5);
      margin-right: 10px;
      min-width: 65px;
      text-align: center;
    }
  }
  .content-box{
    height: 76%;
    margin-bottom: 2px;
    .content{
      height: 15.6%;
      color: #d6e6ff;
      width: 100%;
      background: rgba(139, 170, 219, 0.2);
      padding-left: 10px;
      font-weight: bold;
      margin-bottom: 3px;
      .text{
        width: 70%;
        float: left;
        height: 100%;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        line-height: 32px;
      }
      .data{
        width: 20%;
        float: right;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        font-size: 12px;
      }
      &:last-child{
        margin-bottom: 0;
      }
    }
  }
}
</style>
