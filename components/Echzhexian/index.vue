<template>
    <div id="main" style="width: 1200px;height:400px;" ref='main'></div>
</template>

<script>
  //https://www.jianshu.com/p/926d1d52da7e
  // https://v-charts.js.org/#/skill-demo v-charts
  //echarts参考文档 https://www.echartsjs.com/zh/option.html#legend
  //动态加载数据 https://www.bbsmax.com/A/kvJ33oXXJg
    require.config({
            paths: {
                echarts: 'http://echarts.baidu.com/build/dist'
            }
        });
  var echarts = require('echarts/lib/echarts');
          // 引入提示框和标题组件
          require('echarts/lib/chart/line');
          require('echarts/lib/chart/bar');
          require('echarts/lib/component/tooltip')   // tooltip组件
          require('echarts/lib/component/title')   //  title组件
          require('echarts/lib/component/legend') 

  var option = {}
export default {
  name: 'Echzhexian',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  mounted(){
      this.buildechart()
  },
  methods:{
      buildechart(){
          //var echarts = require('echarts');
          

            var myChart = echarts.init(document.getElementById('main'));

                option = {
                                     title : {
                                          text: '未来一周气温变化',
                                          subtext: '纯属虚构'
                                      },
                                    tooltip : {
                                            trigger: 'axis'
                                    },
                                    legend: {
                                            data:['邮件营销','联盟广告','视频广告','直接访问','搜索引擎']
                                    },
                                    toolbox: {
                                           mark : {show: true},
                                          dataView : {show: true, readOnly: false},
                                          magicType : {show: true, type: ['line', 'bar']},
                                          restore : {show: true},
                                          saveAsImage : {show: true}
                                    },
                                    calculable : true,
                                    xAxis : [
                                            {
                                                    type : 'category',
                                                    boundaryGap : false,
                                                    data : ['周一','周二','周三','周四','周五','周六','周日','周八','周九'],
                                                    axisLabel:{
                                                      interval:1,
                                                    }
                                            }
                                    ],
                                    yAxis : [
                                            {
                                                    type : 'value',
                                                      
                                            },
                                            {
                                                    type : 'value',
                                                      
                                            }
                                    ],
                                    series : [
                                            {
                                                    name:'邮件营销',
                                                    type:'line',
                                                    stack: '总量',
                                                    smooth:true,
                                                    areaStyle: {normal:{}},
                                                    itemStyle: {normal: {areaStyle: {type: 'default'}}},    
                                                    data:[120, 132, 101, 134, 90, 230, 210, 100,300]
                                            },
                                            {
                                                    name:'联盟广告',
                                                    type:'line',
                                                    stack: '总量',
                                                    smooth:true,
                                                    itemStyle: {normal: {areaStyle: {type: 'default'}}},
                                                    data:[220, 182, 191, 234, 290, 330, 310,100, 234]
                                            },
                                            {
                                                    name:'视频广告',
                                                    type:'line',
                                                    stack: '总量',
                                                    smooth:true,
                                                    itemStyle: {normal: {areaStyle: {type: 'default'}}},
                                                    data:[150, 232, 201, 154, 190, 330, 410,100, 234]
                                            },
                                            {
                                                    name:'直接访问',
                                                    type:'line',
                                                    stack: '总量',
                                                    smooth:true,
                                                    itemStyle: {normal: {areaStyle: {type: 'default'}}},
                                                    data:[320, 332, 301, 334, 390, 330, 320,100, 234]
                                            },
                                            {
                                                    name:'搜索引擎',
                                                    type:'line',
                                                    stack: '总量',
                                                    smooth:true,
                                                    itemStyle: {normal: {areaStyle: {type: 'default'}}},
                                                    data:[820, 932, 901, 934, 1290, 1330, 1320,800,740,1000]
                                            }
                                    ]
                            };

                // 为echarts对象加载数据 
                myChart.setOption(option); 

                                    // 2异步加载数据
                    // $.get('/admin/js/data1.json').done(function (data) {
                    //     // 填入数据
                    //     myChart1.setOption({
                    //         xAxis: {
                    //             type: 'category',
                    //             boundaryGap: false,
                    //             data: data.dataX2
                    //         },
                    //         series: [{
                    //             name: '销量',
                    //             data: data.data1
                    //         }]
                    //     });
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
