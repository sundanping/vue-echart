<template>
<div class="lists">
  <span class="cheek_topRight"></span>
  <span class="cheek_botleft"></span>
  <div class="title">
    <span>南京两名小伙与国庆中秋同名 因工作需要无缘假期</span>
  </div>
  <div class="canvas-box">
    <div class="canvas-left">
      <div class="title-test">分渠道热度走势</div>
      <div id="heat" :style="{width: '100%', height: '100%'}"></div>
    </div>
    <div class="canvas-middle">
      <div class="canvas-middle-top">
        <div class="title-test">男女比例</div>
        <div id="man" :style="{width: '100%', height: '100%'}"></div>
      </div>
      <div class="canvas-middle-bot">
        <div class="title-test">情感分析</div>
        <div id="emotional" :style="{width: '100%', height: '100%'}"></div>
      </div>
    </div>
    <div class="canvas-right">
      <div class="canvas-right-top">
        <div class="title-test">年龄层次</div>
        <div id="age" :style="{width: '100%', height: '130%'}"></div>
      </div>
      <div class="canvas-right-bot">
        <div class="title-test">区域分布</div>
        <div id="map" :style="{width: '50%', height: '100%'}"></div>
        <div id="column" :style="{width: '50%', height: '100%'}"></div>
      </div>
    </div>
  </div>
</div>
</template>
<script>
  export default {
    name: 'right',
    data () {
      return {
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
        let heat = this.$echarts.init(document.getElementById('heat'))
        let man = this.$echarts.init(document.getElementById('man'))
        let emotional = this.$echarts.init(document.getElementById('emotional'))
        let age = this.$echarts.init(document.getElementById('age'))
        let map = this.$echarts.init(document.getElementById('map'))
        let column = this.$echarts.init(document.getElementById('column'))
        // 绘制图表 heat
        heat.setOption({
          color: ['#ce4272', '#0554f5', '#f3972e'],
          textStyle: {
            color: '#fff'
          },
          legend: {
            right: '60',
            top: '10',
            textStyle: {
              color: '#fff'
            },
            data: ['网站', '微信', '微博']
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
              axisTick: {
                show: false,  // 是否显示坐标轴刻度。默认显示 true 设置为不显示
                alignWithLabel: true // 刻度线和标签对齐
              },
              axisLine: {
                lineStyle: {
                  color: ['#71a4f2'],
                  width: '1',
                  type: 'solid'
                }
              }, // 刻度线
              data: ['09-23', '09-24', '09-25', '09-26', '09-27', '09-28', '09-29']
            }
          ],
          yAxis: [
            {
              type: 'value',
              name: '数量',
              axisTick: {
                show: false,
                alignWithLabel: true
              },  // 是否显示坐标轴刻度。默认显示 true 设置为不显示
              axisLine: {
                lineStyle: {
                  color: ['#71a4f2'],
                  width: '1',
                  type: 'solid'
                }
              },  // 刻度线
              splitLine: {
                lineStyle: {
                  color: ['rgba(113,164,242,0.1)'],
                  width: '1',
                  type: 'solid'
                }
              },  // 背景分界线
              axisPointer: {
                show: true,
                type: 'shadow'
              }  // 设置 移入阴影
            }

          ],
          series: [
            {
              name: '网站',
              type: 'line',
              smooth: true,
              stack: '总量',
              data: [4, 3, 2, 1, 1, 3, 4]
            },
            {
              name: '微信',
              type: 'line',
              smooth: true,
              stack: '总量',
              data: [1, 1, 2, 1, 1, 3, 3]
            },
            {
              name: '微博',
              type: 'line',
              smooth: true,
              stack: '总量',
              data: [9, 6, 5, 9, 12, 8, 6]
            }
          ]
        })
        // 绘制图表 man
        man.setOption({
          color: ['#db546c', '#007dde'],
          textStyle: {
            color: '#fff'
          },
          series: [
            {
              name: '男女比例',
              type: 'pie',
              radius: '55%',
              center: ['50%', '50%'],
              label: {
                normal: {
                  show: true,
                  formatter: '{b} \n {d}%',
                  textStyle: {
                    fontSize: '12',
                    fontWeight: 'bold'
                  }
                },
                emphasis: {
                  show: true,
                  formatter: '{b} \n {d}%',
                  textStyle: {
                    fontSize: '14',
                    fontWeight: 'bold'
                  }
                }
              },  // 折线
              labelLine: {
                normal: {
                  color: '#fff',
                  length: 7,
                  length2: 5,
                  show: true
                }
              }, // 移入之后
              data: [
                {value: 400, name: '男生', selected: true},
                {value: 400, name: '女生'}
              ]
//              itemStyle: {
//                emphasis: {
//                  shadowBlur: 10,
//                  shadowOffsetX: 0,
//                  shadowColor: 'rgba(0, 0, 0, 0.5)'
//                }
//              }
            }
          ]
        })
        // 绘制图表 emotional
        emotional.setOption({
          color: ['#ce4272', '#0554f5', '#f3972e', '#008aed', '#14da7d'],
          textStyle: {
            color: '#fff'
          },
          legend: {
            data: []
          },
          series: [
            {
              name: '情感分析',
              type: 'pie',
              radius: ['50%', '70%'], // 圆环
              avoidLabelOverlap: false,
              label: {
                normal: {
                  show: true,
                  formatter: '{b} \n {d}%',
                  textStyle: {
                    fontSize: '12',
                    fontWeight: 'bold'
                  }
                },
                emphasis: {
                  show: true,
                  formatter: '{b} \n {d}%',
                  textStyle: {
                    fontSize: '14',
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
                {value: 335, name: '正面'},
                {value: 310, name: '中面'},
                {value: 400, name: '负面'}
              ]
            }
          ]
        })
        // 绘制图表 age
        age.setOption({
          color: ['#4da2fe'],
          textStyle: {
            color: '#fff'
          },
          xAxis: [
            {
              axisTick: {
                show: false,  // 是否显示坐标轴刻度。默认显示 true 设置为不显示
                alignWithLabel: true // 刻度线和标签对齐
              },
              axisLine: {
                lineStyle: {
                  color: ['#71a4f2'],
                  width: '1',
                  type: 'solid'
                }
              }, // 刻度线
              data: ['12岁以下', '13-25岁', '26-35岁', '36-45岁', '46岁以上']
            }
          ],
          yAxis: [
            {
              axisLabel: {
                interval: 15,   // 15 为一个刻度单位 距离
                formatter: '{value}%'
              },
              axisTick: {
                show: false,
                alignWithLabel: true
              },  // 是否显示坐标轴刻度。默认显示 true 设置为不显示
              axisLine: {
                lineStyle: {
                  color: ['#71a4f2'],
                  width: '1',
                  type: 'solid'
                }
              },  // 刻度线
              splitLine: {
                lineStyle: {
                  color: ['rgba(113,164,242,0.1)'],
                  width: '1',
                  type: 'solid'
                }
              },  // 背景分界线
              axisPointer: {
                show: true,
                type: 'shadow'
              }  // 设置 移入阴影
            }

          ],
          series: [
            {
              name: '年龄层次',
              type: 'bar',
              barWidth: '50%',
              itemStyle: {
                normal: {
                  label: {
                    show: true,
                    position: 'top',
                    formatter: '{c}%'
                  }
                }
              },
              data: [
                {value: 8, name: '12岁以下'},
                {value: 40, name: '13-25岁'},
                {value: 32, name: '26-35岁'},
                {value: 13, name: '36-45岁'},
                {value: 7, name: '46岁以上'}
              ]
            }
          ]
        })
        // 绘制图表 map
        map.setOption({
          color: ['#ce4272', '#0554f5', '#f3972e', '#008aed'],
          textStyle: {
            color: '#fff'
          },
          visualMap: {
            show: false,
            min: 0,
            // max: 2500,
            left: 'right',
            top: 'bottom',
            inRange: {
              color: ['#6d9ce6', '#0763f3']
            },
            textStyle: {
              color: '#fff'
            },
            itemWidth: 10,
            itemHeight: 70,
            text: ['高', '低'],
            calculable: true
          },
          toolbox: {
            show: false
          },
          series: [
            {
              name: '区域分布',
              type: 'map',
              mapType: 'china',
              roam: false,
              label: {
                normal: {
                  show: false
                },
                emphasis: {
                  show: true
                }
              },
              data: [12, 465, 145, 478, 145, 249]
            }
          ]
        })
        column.setOption({
          color: ['#ce4272', '#0554f5', '#f3972e', '#008aed'],
          textStyle: {
            color: '#fff'
          },
          grid: {
            left: '3%',
            right: '6%',
            bottom: '3%',
            top: 10,
            containLabel: true
          },
          xAxis: {
            show: false
          },
          yAxis: {
            type: 'category',
            axisLine: {
              lineStyle: {
                width: '0'
              }
            },
            axisTick: {
              show: false
            },
            data: ['北京', '天津', '广东', '上海', '江苏', '辽宁']
          },
          series: [
            {
              name: '区域分布',
              type: 'bar',
              barMaxWidth: 20,
              data: [
                {value: '72.0', kRegion: '北京', count_kRegion: 18},
                {value: '71.0', kRegion: '天津', count_kRegion: 18},
                {value: '62.0', kRegion: '广东', count_kRegion: 16},
                {value: '47.0', kRegion: '上海', count_kRegion: 12},
                {value: '45.0', kRegion: '江苏', count_kRegion: 11},
                {value: '26.0', kRegion: '辽宁', count_kRegion: 7}
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
    width: 100%;
  }
  .canvas-box{
    height: 85%;
    width:100%;
    .title-test{
      position: absolute;
      left: 5px;
      top: 5px;
      color: #fff;
      padding: 0 5px;
      background-color: #0763f3;
      border-radius: 3px;
    }
    .canvas-left{
      width: 36%;
      height: 100%;
      float: left;
      background: rgba(23, 48, 100, 0.4);
      position: relative;
      margin-right: 3px;
      padding: 3px;
    }
    .canvas-middle{
      width: 24%;
      height: 100%;
      float: left;
      margin-right: 3px;
      .canvas-middle-top{
        height: 49%;
        margin-bottom: 1%;
        background: rgba(23, 48, 100, 0.4);
        position: relative;
        padding: 3px;
      }
      .canvas-middle-bot{
        height: 49%;
        margin-bottom: 1%;
        background: rgba(23, 48, 100, 0.4);
        position: relative;
        padding: 3px;
      }
    }
    .canvas-right{
      width: 39%;
      height: 100%;
      float: left;
      .canvas-right-top{
        height: 49%;
        margin-bottom: 1%;
        background: rgba(23, 48, 100, 0.4);
        position: relative;
        padding: 3px;
      }
      .canvas-right-bot{
        height: 49%;
        margin-bottom: 1%;
        background: rgba(23, 48, 100, 0.4);
        position: relative;
        padding: 3px;
      }
    }
    #map{
      float: left;
    }
    #column{
      float: left;
    }
  }
}
</style>
