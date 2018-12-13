<template>
  <div class="initbox">
    <div class="is-background"></div>
    <el-row :gutter="20">
      <el-col :span="24"><div class="grid-content bg-purple">

      </div></el-col>
    </el-row>
    <el-row :gutter="20">
      <el-col :span="18"><div class="grid-content bg-purple content">

      </div></el-col>
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
        <div v-else>
          <el-button>请登录</el-button>
        </div>
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

      }

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
  .headimg{
    height: 100px;
    width: 100px;
    background: cornflowerblue;
    margin: 0 auto 20px;
    position: relative;
    top:20px;
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
