<template>
  <div class="sygg"  ref="sygg">
      <div class="container">
               <div class="zxgg">
                  <div class="tablecont"  style="background:#fff;border-radius:4px;box-shadow: 0 0 4px 0 rgba(0,0,0,0.10);">  
                    <h3>广告创建成功</h3>
                   <el-table
                    :data="tableData.slice((limitePage.page-1)*limitePage.limit,limitePage.limit*limitePage.page)" 
                    border
                    style="width: 100%"
                   id="zxtable" @cell-click="Cellclick" >
                            <el-table-column
                              prop="appName"
                              label="应用名称"
                              width="180">
                            </el-table-column>
                            <el-table-column
                              prop="createTime"
                              label="创建时间"
                              width="180">
                            </el-table-column>
                            <el-table-column
                              prop="appType"
                              label="产品类型">
                            </el-table-column>
                            <el-table-column
                              prop="appVersion"
                              label="平台版本">
                               <template slot-scope="scope">
                                <a @click="cancelDialog(scope.row)" style="color:blue;cursor:pointer">{{scope.row.appVersion}}</a>
                               </template>
                            </el-table-column>
                            <el-table-column
                              prop="address"
                              label="推广计划/进行中计划">
                            </el-table-column>
                      </el-table>
                  </div>    
                  <div class="block">
                   <!-- 分页 paging -->
                   <el-pagination
                      @size-change="handleSizeChange"   
                      @current-change="handleCurrentChange"
                      :current-page="limitePage.page"
                      :page-sizes="[2, 4]"
                      :page-size="limitePage.limit"
                      layout="total, sizes, prev, pager, next, jumper"
                      :total="tableData.length">
                    </el-pagination>
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
          appType: '百度输入法',
          appVersion:'安卓',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
           appName:'和平精英',
          createTime:'2016-05-03',
          appType: '百度输入法',
          appVersion:'安卓',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
           appName:'和平精英',
          createTime:'2016-05-04',
          appType: '百度输入法',
          appVersion:'安卓',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
           appName:'百度输入法',
          createTime:'2016-05-05',
          appType: '百度输入法',
          appVersion:'安卓',
          address: '上海市普陀区金沙江路 1516 弄'
        }],
            limitePage:{
                limit:2,//每页显示数据条目个数
                page:1 //当前页码
              }
    }
  },
  mounted(){
        this.$refs.sygg.style.height = window.innerHeight-89+'px';
  },
    methods:{
      //某行点击事件
      Cellclick(row,column,event,cell,rowIndex){
           console.log(row)
          console.log(1,row.appName,rowIndex)
      },
       // 确定选择案件
        cancelDialog(row) {
            console.log(row)
      },
      //分页功能实现
          handleClick(row) {
              console.log(row);
            },
            handleSizeChange(val) {
              this.limitePage.limit = val;
            },
            handleCurrentChange(val) {
              this.limitePage.page = val
            }


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
.zxgg{margin-top: 22px}
 >>> .el-pagination span:not([class*=suffix]){display: none}
    >>> .el-pagination{    text-align: right;    margin-top: 15px;}
    >>> .el-pager li.active{background: #006CFF;border-radius: 4px;color: #fff}
    >>> .el-pager li{padding: 0;min-width: 28px;background: #F4F7F9;}
    >>> .el-pagination button:disabled{    background: #F4F7F9;}
    >>> .el-pagination .btn-next{background: #F4F7F9;}
    >>> .el-pager{background: #F4F7F9;}
    >>> .el-pagination .btn-prev{background: #F4F7F9;}
</style>