<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <router-view/> -->
    <p>儿子的名字是:{{sonName}}</p>
    <Son @tellSonName='listenSon' :fatherName='name'></Son>
    <Daughter>
      <p slot="header">我是头部</p>
      <p slot="footer">我是尾部</p>
    </Daughter>
  </div>
</template>

<script>
import Son from './views/Son'
import Daughter from './views/Daughter'
export default {
  name: 'app',
  components: {
    Son,
    Daughter
  },
  data () {
    return {
      name: '父组件',
      sonName: ''
    }
  },
  methods: {
    listenSon (val) {
      this.sonName = val
    }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
