<template>
  <div class="initbox">
    <div class="is-background"></div>
    <headers/>
    <content/>
    <userinfo class="userinfo"/>
  </div>

</template>

<script>

    import Content from "./content";
    import Userinfo from "./userinfo";
    import Headers from "./headers";
    export default {
        name: "MainWindow",
      components: {Headers, Userinfo, Content},
    }
</script>

<style scoped>
  .initbox{
    width: 1000px;
    margin: 0 auto;
  }
  .is-background{

    background-image: url("../../assets/MT.jpg");
  }
  .userinfo{
    margin-top: 10px;
    float: right;
  }
</style>
