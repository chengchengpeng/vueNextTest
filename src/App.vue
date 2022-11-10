<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld ref="helloWorld" :nums="nums" msg="Welcome to Your Vue.js App">
    <template #header="prop">
   <div> header 插槽的内容放这里{{prop.total}}{{prop.message}}</div>
  </template>
  <div>keykeykeykey</div>
  </HelloWorld>
  <!-- <button  @click="handelClick">点击</button> -->
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      nums:2
    }
  },
  methods:{
    handelClick() {
      this.nums = this.nums+ 1
      this.$refs.helloWorld.key = 100
       this.$refs.helloWorld.setupValue = 1000
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
