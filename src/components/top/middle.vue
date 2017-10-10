<template>
<div class="lists">
  <span class="cheek_topRight"></span>
  <span class="cheek_botleft"></span>
  <div class="title">
    <span>生产内容统计</span>
  </div>
  <div class="contents">
    <div id="myChart" :style="{width: '100%', height: '100%'}"></div>
  </div>
</div>
</template>
<script>
export default {
  name: 'topMiddle',
  mounted () {
    this.drawLine()
  },
  methods: {
    drawLine () {
      // 基于准备好的dom，初始化echarts实例
      let myChart = this.$echarts.init(document.getElementById('myChart'))
      // 绘制图表
      myChart.setOption({
        color: ['#8d6cf9', '#f36764', '#fc8e26', '#14da7e'],
        legend: {
          right: '60',
          top: '10',
          textStyle: {
            color: '#fff'
          },
          data: ['文稿', '视频', '专题', '图集']
        },
        tooltip: {
          trigger: 'axis'
        },
        textStyle: {
          color: '#fff'
        },
        grid: {
          left: '3%',
          right: '7%',
          bottom: '5%',
          containLabel: true
        },
        xAxis: [
          {
            type: 'category',
            name: '日期',
            boundaryGap: false,
            axisLine: {
              lineStyle: {
                color: ['#71a4f2'],
                width: '1',
                type: 'solid'
              }
            },
            axisTick: {
              show: false,
              alignWithLabel: true
            },
            data: ['09-23', '09-24', '09-25', '09-26', '09-27', '09-28', '09-29']
          }
        ],
        yAxis: [
          {
            type: 'value',
            name: '数量',
            axisLine: {
              lineStyle: {
                color: ['#71a4f2'],
                width: '1',
                type: 'solid'
              }
            },
            axisTick: {
              show: false,
              alignWithLabel: true
            },
            splitLine: {
              lineStyle: {
                color: ['rgba(113,164,242,0.3)'],
                width: '1',
                type: 'dashed'
              }
            },
            axisPointer: {
              show: true
            }
          }
        ],
        series: [
          {
            name: '文稿',
            type: 'line',
            smooth: true,
            stack: '总量',
            areaStyle: {normal: {}},
            data: [4, 3, 2, 1, 1, 3, 4]
          },
          {
            name: '视频',
            type: 'line',
            smooth: true,
            stack: '总量',
            areaStyle: {normal: {}},
            data: [4, 3, 2, 1, 1, 3, 4]
          },
          {
            name: '专题',
            type: 'line',
            smooth: true,
            stack: '总量',
            areaStyle: {normal: {}},
            data: [4, 3, 2, 1, 1, 3, 4]
          },
          {
            name: '图集',
            type: 'line',
            smooth: true,
            stack: '总量',
            areaStyle: {normal: {}},
            data: [4, 3, 2, 1, 1, 3, 4]
          }
        ]
      })
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
  border: 1px solid #72a4f2;
  position: relative;
  padding: 5px;
  background: rgba(16, 43, 85, 0.6);
  overflow: hidden;
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
    height: calc(100% - 12%);
    width: 100%;
    color: #fff;
  }
}
</style>
