<template>
  <div class="hello">
    <button v-on:click="clickHandler('dadadadada')" type="button" name="button">按钮</button>
    <p v-show="flag" >Hello</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      flag:true
    }
  },
  methods:{
    clickHandler(data){
      console.log(data);
      this.flag=!this.flag;
    }
  }
}
</script>

<style scoped>

</style>
