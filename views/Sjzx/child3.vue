<template>
  <div class="hello">
      <div class="container">
            <el-row style="font-family: PingFangSC;font-size: 12px;color: #006AFF;">
                              <el-button type="text" id="fanhui">< 返回</el-button>
          </el-row>
          <h4>推广计划：百度输入法 - 开屏</h4>
          <el-row style="background: #FFFFFF;box-shadow: 0 0 4px 0 rgba(0,0,0,0.10);border-radius: 4px;margin-bottom:21px;">
                <div class="tabhead">
                      <a href="javascript:void(0)" class="cur">今日</a>
                      <a href="javascript:void(0)">昨日</a>
                      <a href="javascript:void(0)">近7日</a>
                      <a href="javascript:void(0)">近30日</a>
                      <a href="javascript:void(0)" class="last">全部日期</a>
                </div>
                <div>
                     <img src="/static/zdymb.png"  style="width:108px">
                </div>
                <el-row class="shumu">
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div class="text">曝光量</div>
                          </div>
                          <div>
                                <div  class="num"><span>1737</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div class="text">点击量</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">点击人数</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">点击率</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">点击激活</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">点击激活人数</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">点击激活率</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">注册</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">登陆</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">拍下订单设备数</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">付费设备数</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">拍下金额</div>
                          </div>
                          <div>
                                <div class="num"><span>173897</span><img src="/static/ask.png"  style="width:15px"></div>
                                <div  class="text">付费金额</div>
                          </div>
                </el-row>
         </el-row>
         <el-row style="background: #FFFFFF;box-shadow: 0 0 4px 0 rgba(0,0,0,0.10);border-radius: 4px;margin-bottom:21px;">
                <Echzhexian/>
        </el-row>
        <el-row style="display:flex;">
            <el-row style="background: #FFFFFF;box-shadow: 0 0 4px 0 rgba(0,0,0,0.10);border-radius: 4px;margin-bottom:21px;width:590px;margin-right:20px">
                    付费漏斗分析
            </el-row>
            <el-row style="background: #FFFFFF;box-shadow: 0 0 4px 0 rgba(0,0,0,0.10);border-radius: 4px;margin-bottom:21px;width:590px;">
                    付费地区分析
            </el-row>
      </el-row>
      </div>
  </div>
</template>

<script>
import Echzhexian from '@/components/Echzhexian';
export default {
  name: 'Child3',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
   components : {
        Echzhexian
    },
    mounted(){
         this.axios.post('/api/adver/getAdverPlanTotalReport?current=1&size=5').then((res)=>{
              console.log(res)
         })
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{width: 1200px;margin: 0 auto;}
h4{font-size: 14px;color: #999999;-webkit-margin-before: 0;}
.tabhead{background: #F8F9FA;display: flex;flex-direction:row;height: 57px;line-height: 57px}
.tabhead a{opacity: 0.7;font-family: PingFangSC;font-size: 14px;color: #333333;text-decoration: none;width: 127px;text-align: center;border-right: solid 1px #ECECEC;}
.tabhead a.last{border-right: 0}
.tabhead a.cur{background: #fff}
.shumu{display: flex;flex-direction:row;padding: 0 10px;    flex-wrap: wrap;    margin-left: 11px;margin-bottom:25px;}
.shumu>div{background: url('/static/jhbg.png') no-repeat top center;width: 181px;height: 118px;background-size: 100%;text-align: center;line-height: 100%;margin: 12px 6px 0 6px;display: flex;flex-direction:column;align-items:center;justify-content:center;}
.shumu>div div.num{font-size: 26px;color: #323A3D;    margin-bottom: 14px;}
.shumu>div div.text{font-size: 18px;color: #909396;}
</style>
