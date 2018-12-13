<template>
  <div class="initbox">
    <div class="is-background"></div>
    <el-row :gutter="20"><!-- 头部 -->
      <el-col :span="24"><div class="grid-content bg-purple">

      </div></el-col>
    </el-row>
    <div class="LeftContent">
      <div class="content">
        <!-- 显示帖子内容 -->
        <ul>
          <li></li>
        </ul>
      </div>
      <!-- 翻页组件 -->
      <div class="block">
       <el-pagination class="page"
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
          :current-page="currentPage4"
          :page-sizes="[10, 20, 30, 40]"
          :page-size="50"
          layout="total, sizes, prev, pager, next, jumper"
          :total="50">
        </el-pagination>
      </div>
    </div>
    <!-- 用户信息栏 -->
    <el-row>
      <el-col :span="6"><div class="grid-content bg-purple content" id="infos">
        <div v-if="isLogin">
        <div class="headimg"></div>
        <ul class="userinfo">
          <li v-for= "item in userinfos">用户名：{{ item.name }}</li>
          <li v-for= "item in userinfos">论坛等级：Lv{{ item.leve }}</li>
          <li v-for= "item in userinfos">发帖数量：{{ item.postSun }}</li>
          <li v-for= "item in userinfos">主题数量：{{ item.titleSUn }}</li>
          <li v-for= "item in userinfos">积分剩余：{{ item.point }}</li>
        </ul>
        </div>
        <div v-else class="Tologin">
          <el-button class="TologinBtn">请登录</el-button>
        </div>
        <el-button @click="an">切换登录状态</el-button>
      </div></el-col>
    </el-row>
  </div>

</template>

<script>
    export default {
        name: "MainWindow",
      data() {
        return {
            isLogin:true,
            userinfos:[
              {
                name:"Username",
                leve:"5",
                postSun:"30",
                titleSUn:"4",
                point:"312"
              }
            ],
        }
      },
      methods: {
        handleSizeChange(val) {
          console.log(`每页 ${val} 条`);
        },
        handleCurrentChange(val) {
          console.log(`当前页: ${val}`);
        },
        an(){
          this.isLogin=!this.isLogin;
          console.log(this.isLogin);
        }
      },



    }
</script>

<style scoped>
  .el-row {
    margin-bottom: 20px;
  &:last-child {
     margin-bottom: 0;
   }
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
  .grid-content{
    height: auto;
  }
  .initbox{
    width: 1000px;
    margin: 0 auto;
  }
  .is-background{
    width: 100%;
    height: 100%;
    background-image: url("../../assets/MT.jpg");
  }
  .LeftContent{

    background: cornflowerblue;
    float: left;
    height: 1000px;
    width: 740px;
  }
  .content{
    height: 800px;
  }
  .block{
    position: relative;
    bottom: 0;
    z-index: 99;
  }
  .headimg{
    height: 100px;
    width: 100px;
    background: cornflowerblue;
    margin: 0 auto 20px;
    position: relative;
    top:20px;
  }
  .Tologin{
    height: 200px;
    width: 80px;
   margin:auto ;
  }
  .TologinBtn{
    margin-top: 100px;
  }
  .userinfo{
    margin: 30px auto;
    padding: 0 auto;
    list-style: none;
  }
  #infos{
    height: 400px;

  }
  .userinfo>li{
    margin: 4px auto;
  }
</style>
