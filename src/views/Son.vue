<template>
  <div id="son">
    <p>{{myName}}</p>
    <p>父亲的名字是：{{fatherName}}</p>
    <p>妹妹的名字是：{{sisterName}}</p>
    <input type="button" value="告诉父亲我的名字" @click="tellFather">
  </div>
</template>

<script>
import eventBus from '../utils/eventBus.js'
export default {
  data () {
    return {
      myName: '儿子组件',
      sisterName: ''
    }
  },
  // props: ['fatherName'],
  props: {
    fatherName: String
  },
  methods: {
    tellFather () {
      this.$emit('tellSonName', this.myName)
    }
  },
  mounted () {
    eventBus.$on('toBro', (data) => {
      // console.log(data)
      this.sisterName = data
    })
  }
}

</script>

<style scoped>
  #son{
    border: 1px solid #000;
  }
</style>
