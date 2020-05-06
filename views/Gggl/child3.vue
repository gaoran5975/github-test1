<template>
  <div class="child2">
       <el-main>
              <div class="container" id="xjgg">
                     <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
                        <el-row  style="background:#fff;padding-left: 50px;border-radius: 4px;">       
                               <h3>创建广告计划</h3>
                              <el-form-item label="广告名称" prop="appName"  class="elform1">
                                  <el-select v-model="ruleForm.appName" placeholder="请选择">
                                                <el-option label="区域一" value="shanghai">
                                                </el-option>
                                   </el-select>
                              </el-form-item> 
                                <el-form-item label="出价" prop="unitPrice" class="elform1">
                                      <el-input v-model="ruleForm.unitPrice"   placeholder=""></el-input><span style="position: absolute;left:180px">元/CPC</span>
                              </el-form-item> 
                              <el-form-item label="每日预算" prop="everydayBudget"  class="elform1">
                                      <el-input v-model="ruleForm.everydayBudget"   placeholder=""></el-input>
                              </el-form-item> 
                              <el-form-item label="总预算" prop="totalBudget"  class="elform1">
                                      <el-input v-model="ruleForm.totalBudget"   placeholder=""></el-input>
                              </el-form-item> 
                               <el-form-item label="推广方式" prop="putLocation"  class="elform1">
                                  <el-select v-model="ruleForm.putLocation" placeholder="开屏">
                                                <el-option label="区域一" value="shanghai">
                                                </el-option>
                                   </el-select>
                              </el-form-item>
                               <el-form-item label="推广素材"　 class="elform1">
                                      <el-input 　 placeholder="对应推广方式提供素材"></el-input>
                              </el-form-item>
                              <el-form-item label="上传素材" required class="elform-scsc">
                                   <el-col :span="7"> 
                                                <el-upload
                                                  class="avatar-uploader"
                                                  action="https://jsonplaceholder.typicode.com/posts/"
                                                  :show-file-list="false"
                                                  :on-success="handleAvatarSuccess"
                                                  :before-upload="beforeAvatarUpload">
                                                  <img v-if="imageUrl1" :src="imageUrl1" class="avatar">
                                                  <i v-else class="el-icon-plus avatar-uploader-icon"></i>
                                                </el-upload>
                                    </el-col>
                                    <el-col class="line" :span="1"></el-col>    
                                     <el-col :span="7"> 
                                            <el-upload
                                                  class="avatar-uploader"
                                                  action="https://jsonplaceholder.typicode.com/posts/"
                                                  :show-file-list="false"
                                                  :on-success="handleAvatarSuccess"
                                                  :before-upload="beforeAvatarUpload">
                                                  <img v-if="imageUrl2" :src="imageUrl2" class="avatar">
                                                  <i v-else class="el-icon-plus avatar-uploader-icon"></i>
                                                </el-upload>
                                     </el-col>  
                                    <el-col class="line" :span="1"></el-col> 
                                     <el-col :span="7">
                                               <el-upload
                                                  class="avatar-uploader"
                                                  action="https://jsonplaceholder.typicode.com/posts/"
                                                  :show-file-list="false"
                                                  :on-success="handleAvatarSuccess"
                                                  :before-upload="beforeAvatarUpload">
                                                  <img v-if="imageUrl3" :src="imageUrl3" class="avatar">
                                                  <i v-else class="el-icon-plus avatar-uploader-icon"></i>
                                                </el-upload>
                                     </el-col>
                                     <el-col class="line" :span="3"></el-col>   
                              </el-form-item>
                              <el-row style="    padding-bottom: 10px;">
                                        <span style="padding-left: 100px;"> 注：118*118  文件不超过100KB</span>      
                              </el-row>
                              <el-form-item label="流量定位" prop="" 　 class="elform1">
                                      <el-input　 placeholder=""></el-input>
                              </el-form-item>   
                              <el-form-item label="地域限制"　 prop="" 　 class="elform1">
        								    <el-checkbox-group v-model="ruleForm.diyu">
        								      <el-checkbox label="北京" name="type"></el-checkbox>
        								      <el-checkbox label="上海" name="type"></el-checkbox>
        								    </el-checkbox-group>
        							</el-form-item>
                                      <el-form-item label="活动时间" required>
        									           <el-form-item prop="date1">
                                            <el-date-picker
                                          v-model="ruleForm.date1"
                                          value-format="yyyy-MM-dd"
                                          type="daterange"
                                          range-separator="至"
                                          start-placeholder="开始日期"
                                          end-placeholder="结束日期">
                                        </el-date-picker> 
                                   </el-form-item> 
        							　　</el-form-item> 
        							 <el-form-item label="媒体类型"　 prop="" class="elform-mtlx">
        								    <el-checkbox-group v-model="ruleForm.check_mtlx">
        										      <el-checkbox label="休闲游戏" name="type"></el-checkbox>
        										      <el-checkbox label="音乐娱乐" name="type"></el-checkbox>
        										      <el-checkbox label="美妆生活" name="type"></el-checkbox>
        										      <el-checkbox label="办公高效" name="type"></el-checkbox>
        										      <el-checkbox label="运动健康" name="type"></el-checkbox>
        										      <el-checkbox label="美食生活" name="type"></el-checkbox>
        										      <el-checkbox label="便捷工具" name="type"></el-checkbox>
        										      <el-checkbox label="学习工具" name="type"></el-checkbox>
        										      <el-checkbox label="生活方式" name="type"></el-checkbox>
        										      <el-checkbox label="旅游出行" name="type"></el-checkbox>
        								    </el-checkbox-group>
        							</el-form-item>       
        							<el-form-item label="设置金额"　 prop="">
        								    <el-checkbox-group v-model="ruleForm.check_szje">
        										      <el-checkbox label="500-1000元" name="type"></el-checkbox>
        										      <el-checkbox label="500-1000元" name="type"></el-checkbox>
        										      <el-checkbox label="2001-3000元" name="type"></el-checkbox>
        										      <el-checkbox label="3001-5000元" name="type"></el-checkbox>
        										      <el-checkbox label="5001元以上" name="type"></el-checkbox>										
        								    </el-checkbox-group>
        							</el-form-item>   
        							<el-form-item label="系统版本"　 prop="">
        								    <el-checkbox-group v-model="ruleForm.check_xtbb">
        										      <el-checkbox label="IOS 9" name="type"></el-checkbox>
        										      <el-checkbox label="IOS 10" name="type"></el-checkbox>
        										      <el-checkbox label="IOS 11" name="type"></el-checkbox>
        										      <el-checkbox label="IOS 12" name="type"></el-checkbox>										
        								    </el-checkbox-group>
        							</el-form-item>
                  </el-row>
                      <el-row  style="    text-align: right;    margin-top: 13px;">    
							                 <el-form-item size="large">
                                      <el-button style="padding: 12px 23px;height: 29px;line-height:0">取消</el-button>
                                      <el-button type="primary" @click="submitForm('ruleForm')" style="padding: 12px 23px;height: 29px;line-height:0;background:#0A6EFB;">提交</el-button>
                              </el-form-item>  
                    </el-row>                           
                </el-form>
                     
              </div>
          </el-main>
  </div>
</template>

<script>

export default {
  name: 'Child3',
  data() {
      return {
        ruleForm: {
          appName: '',
          unitPrice: '',
          appType: '',
          downloadUrl:'',
          check_mtlx:[],
          check_szje:[],
          check_xtbb: [],
          diyu:[],
          date1:'',
          imageUrl1: '',
          imageUrl2: '',
          imageUrl3: ''
        },
        rules: {
          appName: [
            { required: true, message: '请选择广告名称', trigger: 'change' }
          ],
          unitPrice: [
            { required: true, message: '请输入单价', trigger: 'blur' }
          ],
          everydayBudget: [
            { required: true, message: '请输入每日预算', trigger: 'blur' }
          ],
          totalBudget: [
            { required: true, message: '请输入预算', trigger: 'blur' }
          ],
          putLocation: [
            { required: true, message: '请选择推广方式', trigger: 'change' }
          ],
           diyu: [
            { type: 'array', required: true, message: '请至少选择一个流量限制', trigger: 'change' }
          ],
          date1: [
            { type: 'array', required: true, message: '请选择日期', trigger: 'blur' }
          ]
        },
         value1: '',
        imageUrl: ''
      };
    },
    methods: {
      // everydayBudget，totalBudget 是number需要转换
      // 无流量定位参数
      submitForm(formName) {
        //  获取多选框的值console.log(this.ruleForm.check_mtlx)
        //获取的时间是个数组，
        console.log(this.ruleForm.date1)
        this.$refs[formName].validate((valid) => {
          if (valid) {
            alert('submit!');//有效
          } else {
            // console.log(this.value1[1])
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      },
       handleAvatarSuccess(res, file) {
        this.imageUrl = URL.createObjectURL(file.raw);
        console.log(this.imageUrl)
      },
      beforeAvatarUpload(file) {
        const isJPG = file.type === 'image/jpeg';
        const isLt2M = file.size / 1024 / 1024 < 2;

        if (!isJPG) {
          this.$message.error('上传图片只能是 JPG 格式!');
        }
        if (!isLt2M) {
          this.$message.error('上传图片大小不能超过 2MB!');
        }
        return isJPG && isLt2M;
      }
    }
}
// https://www.cnblogs.com/gaoxingx/p/9111575.html 上传多张图片
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 .container{width: 1200px;margin: 0 auto;}

    h3{font-size: 18px;color: #333333;line-height: 60px;text-align: left; }
    form{margin-left: 50px;font-family: PingFangSC;font-size: 12px;color: #333333;}
    .avatar-uploader .el-upload {
    border: 1px dashed #d9d9d9;
    border-radius: 6px;
    cursor: pointer;
    position: relative;
    overflow: hidden;
  }
  .avatar-uploader .el-upload:hover {
    border-color: #409EFF;
  }
  .avatar-uploader-icon {
    font-size: 28px;
    color: #8c939d;
    width: 178px;
    height: 178px;
    line-height: 178px;
    text-align: center;
  }
  .avatar {
    width: 118px;
    height: 118px;
    display: block;
  }
   form{font-family: PingFangSC;font-size: 12px;color: #333333;}
    /deep/ .el-form-item__label{text-align: left;padding: 0 5px 0 0;}
    /deep/ .elform1 .el-form-item__content{width: 171px;    margin-left: 110px;}
     /deep/ .elform2 .el-radio{width: 42px;    padding: 2px 0;color: transparent; }
    /deep/ .elform2  .el-radio__input.is-checked+.el-radio__label{color: transparent;}
    /deep/ .el-form-item__content .el-input__inner{line-height: 30px;height: 30px;padding: 0 5px;}
    /deep/ .elform-mtlx .el-checkbox-group{width: 600px}
    .avatar-uploader-icon{width: 118px;height: 118px;line-height: 118px;    border: 1px dashed #C7C4C7;border-radius: 4px;}
    /deep/  .elform-scsc{width: 606px; margin-bottom: 12px;}
</style>
