<template>
  <div class="htshouye">
       <div class="container">
            <el-row style="display:flex;flex-direction:row;justify-content:space-between;margin-top:21px;border:0;background:transparent;box-shadow:none">
                  <el-row style="width:738px;margin-right:22px;">
                  </el-row>
                  <el-row style="width:440px">
                        <h3>最新动态<span><a href="">全部 ></a></span></h3>
                        <ul>
                            <li>【置顶】【通知】新闻动态1</li>
                            <li>【版本更新通知】新闻动态2</li>
                            <li>【版本更新通知】新闻动态3</li>
                            <li>【版本更新通知】新闻动态4</li>
                        </ul>
                  </el-row>
             </el-row>
             <el-row>
                      <h1>概览</h1>
                      <div class="gailan">
                            <div class="xfje">
                                  <div><img src="/static/xfje.png"></div>
                                  <div>昨日消耗金额</div>
                                  <div><span>1111</span>元</div>
                            </div>
                            <div class="tgzs">
                                  <div><img src="/static/tgzs.png"></div>
                                  <div>昨日推广展示</div>
                                  <div><span>3333</span>元</div>
                            </div>
                            <div class="tgdj">
                                  <div><img src="/static/tgdj.png"></div>
                                  <div>昨日推广点击</div>
                                  <div><span>5555</span>元</div>
                            </div>
                      </div>
             </el-row> 
             <el-row>
                      <h1>数据趋势</h1>
             </el-row> 
       </div>
  </div>
</template>

<script>


export default {
  name: 'Htshouye',
  components:{
      
  },
  data () {
     return  {
          songList:''
     }
  },
  created:function(){
                this.getParams();
            },
      methods: {
            getParams:function(){

      },

    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{width: 1200px;margin: 0 auto}
.el-row{background: #FFFFFF;box-shadow: 0 0 4px 0 rgba(0,0,0,0.10);border-radius: 4px;margin-bottom: 21px}
h1{border-bottom: dashed 1px #ECECEC;}
.gailan{display: flex;flex-direction:row;justify-content:space-between;}
</style>
