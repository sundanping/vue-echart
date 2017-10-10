<template>
<div class="lists">
  <span class="cheek_topRight"></span>
  <span class="cheek_botleft"></span>
  <div class="title">
    <span>作品影响力排行</span>
  </div>
  <div class="contents-box">
    <div class="top">
      <div class="top-title">
        <p>阅读量</p>
      </div>
      <ul class="lists-box">
        <li>
          <div>1</div>
          <div>一年来，习近平推动东西扶贫协作再上新台阶</div>
          <div>99568</div>
          <div class="eyes">
            <i class="glyphicon glyphicon-eye-open"></i>
          </div>
        </li>
        <li>
          <div>2</div>
          <div>一年来，习近平推动东西扶贫协作再上新台阶</div>
          <div>99568</div>
          <div class="eyes">
            <i class="glyphicon glyphicon-eye-open"></i>
          </div>
        </li>
        <li>
          <div>3</div>
          <div>一年来，习近平推动东西扶贫协作再上新台阶</div>
          <div>99568</div>
          <div class="eyes">
            <i class="glyphicon glyphicon-eye-open"></i>
          </div>
        </li>
      </ul>
    </div>
    <div class="top">
      <div class="top-title">
        <p>评论</p>
      </div>
      <ul class="lists-box">
        <li>
          <div>1</div>
          <div>一年来，习近平推动东西扶贫协作再上新台阶</div>
          <div>99568</div>
          <div class="text">
            <i class="glyphicon glyphicon-list-alt"></i>
          </div>
        </li>
        <li>
          <div>2</div>
          <div>一年来，习近平推动东西扶贫协作再上新台阶</div>
          <div>99568</div>
          <div class="text">
            <i class="glyphicon glyphicon-list-alt"></i>
          </div>
        </li>
        <li>
          <div>3</div>
          <div>一年来，习近平推动东西扶贫协作再上新台阶</div>
          <div>99568</div>
          <div class="text">
            <i class="glyphicon glyphicon-list-alt"></i>
          </div>
        </li>
      </ul>
    </div>
  </div>
</div>
</template>
<script>
  export default {
    name: 'topRight'

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
    height: 83%;
  }
  .top{
    width: 100%;
    height: 50%;
    margin-bottom: 8px;
    .top-title{
      p{
        min-height: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 60px;
        font-size: 13px;
        background-color: #0763f3;
        -webkit-border-radius: 3%;
        -moz-border-radius: 3%;
        border-radius: 3%;
        color: #fff;
        margin: 0 0 4px;
      }
    }
    .lists-box{
      width: 100%;
      height: 70%;
      li{
        height: 34%;
        color: #d6e6ff;
        width: 100%;
        background: rgba(139, 170, 219, 0.2);
        margin-bottom: 3px;
        padding: 0 10px;
        div{
          float: left;
          height: 100%;
          &:nth-child(1){
            background: #339dff;
            font-size: 16px;
            font-weight: bold;
            padding: 0 2px;
            margin-right: 5px;
            display: flex;
            align-items: center;
            justify-content: center;
          }
          &:nth-child(2){
            font-size: 14px;
            font-weight: bold;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            width: 75%;
            text-align: left;
            display: flex;
            align-items: center;
          }
          &:nth-child(3){
            float: right;
            display: flex;
            align-items: center;
            justify-content: center;
          }
          &:nth-child(4){
            float: right;
            width: 25px;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            i{
              width: 14px;
              height: 14px;
              top: -1px;
            }
          }
        }
      }
    }
  }
}
</style>
