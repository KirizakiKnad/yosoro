<template>
  <div class="userbox">    <!-- 用户信息栏 -->
    <el-row>
    <el-col :span="24"><div class="grid-content bg-purple content" id="infos">
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
        name: "userinfo",
      data(){
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
      methods:{
        an(){
          this.isLogin=!this.isLogin;
          console.log(this.isLogin);
        }
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
    background: #E0E0E0;
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
  .userbox{
    width: 250px;

  }
  .headimg{
    background: darkkhaki;
    width: 100px;
    height: 100px;
    margin: 0 auto;
  }
  .userinfo{
    list-style: none;

  }
  .Tologin{
    width: 250px;
    height: 250px;
  }
  .TologinBtn{
    margin: 82px 82px;
  }
</style>
