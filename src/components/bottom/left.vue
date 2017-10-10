<template>
<div class="lists">
  <span class="cheek_topRight"></span>
  <span class="cheek_botleft"></span>
  <div class="title">
    <span>任务统计</span>
  </div>
  <div class="contents">
    <div id="mission" :style="{width: '100%', height: '100%'}"></div>
  </div>
</div>

</template>
<script>
let clue = require('../../json/clue.json')
export default {
  name: 'left',
  data () {
    return {
      nav: [{name: '互联网'}, {name: '微信'}],
      lists: clue.data
    }
  },
  created () {
  },
  mounted () {
    this.drawLine()
  },
  computed: {
  },
  methods: {
    drawLine () {
      let myChart = this.$echarts.init(document.getElementById('mission'))
      // 绘制图表
      myChart.setOption({
        color: ['#ce4272', '#0554f5', '#f3972e', '#008aed', '#14da7d'],
        textStyle: {
          color: '#fff'
        },
        legend: {
          orient: 'vertical', // 图例列表的布局朝向。
          x: 'right',
          y: 'bottom',
          textStyle: {
            color: '#fff'
          },
          data: ['待处理', '进行中', '待审核', '已完成', '已归档']
        },
        series: [
          {
            name: '任务统计',
            type: 'pie',
            radius: ['50%', '70%'], // 圆环
            avoidLabelOverlap: false,
            label: {
              normal: {
                show: true,
                formatter: ' {d}%',
                textStyle: {
                  fontSize: '14',
                  fontWeight: 'bold'
                }
              },
              emphasis: {
                show: true,
                textStyle: {
                  fontSize: '16',
                  fontWeight: 'bold'
                }
              }
            },  // 折线
            labelLine: {
              normal: {
                show: true
              }
            },  // 移入之后折线
            data: [
              {value: 335, name: '待处理'},
              {value: 310, name: '进行中'},
              {value: 274, name: '待审核'},
              {value: 235, name: '已完成'},
              {value: 400, name: '已归档'}
            ]
          }
        ]
      })
    }
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
  .contents{
    width: 100%;
    height: 88%;
  }
}
</style>
