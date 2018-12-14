<template>
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
</template>

<script>
    export default {
        name: "content",
      data(){

      },
      methods: {
        handleSizeChange(val) {
          console.log(`每页 ${val} 条`);
        },
        handleCurrentChange(val) {
          console.log(`当前页: ${val}`);
        },

      }
    }
</script>

<style scoped>
  .LeftContent{
    background: cornflowerblue;
    height: 1000px;
    width: 740px;
  }
</style>
