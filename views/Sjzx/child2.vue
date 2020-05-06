<template>
  <div class="sygg" ref= "sygg">
      <div class="container">
          <el-row style="font-family: PingFangSC;font-size: 12px;color: #006AFF;">
                              <el-button type="text" id="fanhui">< 返回</el-button>
          </el-row>
           <div class="zxgg">
                <div class="tablecont"  style="background:#fff;border-radius:4px;box-shadow: 0 0 4px 0 rgba(0,0,0,0.10);">            
                    <h3>产品下所有计划</h3>
                    <el-table
                    :data="tableData.slice((limitePage.page-1)*limitePage.limit,limitePage.limit*limitePage.page)" 
                    border
                    style="width: 100%"
                   id="zxtable">
                            <el-table-column
                              prop="appName"
                              label="计划名称"
                              width="180">
                              <template slot-scope="scope">
                                <a @click="Toplan(scope.row)" style="color: #006DFF;cursor:pointer">{{scope.row.appName}}</a>
                            </template>
                            </el-table-column>
                            <el-table-column
                              prop="createTime"
                              label="推广周期"
                              width="180">
                            </el-table-column>
                            <el-table-column
                              prop="status"
                              label="状态"
                              :formatter="formatterColumn">
                            </el-table-column>
                             <el-table-column
                              prop="status"
                              label="点击量">
                            </el-table-column>
                            <el-table-column
                              prop="status"
                              label="点击激活">
                            </el-table-column>
                            <el-table-column
                              prop="appVersion"
                              label="监测配置">
                               <template slot-scope="scope">
                                <a @click="Topeizhi(scope.row)" style="color: #006DFF;cursor:pointer">{{scope.row.appVersion}}</a>
                            </template>
                            </el-table-column>
                            <el-table-column
                              prop="appVersion"
                              label="报表">
                               <template slot-scope="scope">
                                <a @click="Tobaobiao(scope.row)" style="color: #006DFF;cursor:pointer">{{scope.row.appVersion}}</a>
                            </template>
                            </el-table-column>
                      </el-table>
                  </div>
           </div>
      </div>
  </div>
</template>
<script>
export default {
  name:'',
  data () {
    return {
      tableData: [{
          appName:'百度输入法',
          createTime:'2016-05-02',
          status:0,
          appVersion:'安卓',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
           appName:'和平精英',
          createTime:'2016-05-03',
          status: 1,
          appVersion:'安卓',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
           appName:'和平精英',
          createTime:'2016-05-04',
          status: 2,
          appVersion:'安卓',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
           appName:'百度输入法',
          createTime:'2016-05-05',
          status: 3,
          appVersion:'安卓',
          address: '上海市普陀区金沙江路 1516 弄'
        }],
            limitePage:{
                limit:4,//每页显示数据条目个数
                page:1 //当前页码
              }
    }
  },
  mounted(){
        this.$refs.sygg.style.height = window.innerHeight-89+'px';
  },
    methods:{
      //参数没有点击量 ， 点击激活 ， 监测配置 ， 报表
      //状态改成汉字
       formatterColumn(row, column) {
            switch(row.status){
                case 0:
                return '已删除';
                break;

                case 1:
                return '待开始';
                break;

                case 3:
                return '暂停';
                break;
                case 4:
                return '完成 ';
                break;
                default:
                return '未知';
            }
        },
      //某行点击事件
      Cellclick(row,column,event,cell,rowIndex){
           console.log(row)
          console.log(1,row.appName,rowIndex)
      },
      //计划名称点击事件
      Toplan(row){
          console.log(0,row)
      },
       // 配置点击事件
        Topeizhi(row) {
            console.log(1,row)
      },
      //报表点击事件
      Tobaobiao(row){
            console.log(2,row)
      },
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{width: 1200px;margin: 0 auto;}
 .el-table .warning-row {
    background: red;
  }

  .el-table .success-row {
    background: #f0f9eb;
  }
>>> .el-table thead {
    color: #909399;
    font-weight: 500;
}
 .el-table >>> th {
        background-color:  #F8F9FA;padding: 20px 15px 20px;color: #333333;
  }
>>> .el-table tr{height: 59px}
>>> .el-table--enable-row-transition .el-table__body td{padding: 20px 15px 20px}
h3{padding-left: 30px;    padding-top: 14px;}
.zxgg{margin-top: 2px}
 >>> .el-pagination span:not([class*=suffix]){display: none}
    >>> .el-pagination{    text-align: right;    margin-top: 15px;}
    >>> .el-pager li.active{background: #006CFF;border-radius: 4px;color: #fff}
    >>> .el-pager li{padding: 0;min-width: 28px;background: #F4F7F9;}
    >>> .el-pagination button:disabled{    background: #F4F7F9;}
    >>> .el-pagination .btn-next{background: #F4F7F9;}
    >>> .el-pager{background: #F4F7F9;}
    >>> .el-pagination .btn-prev{background: #F4F7F9;}  
</style>