<template>
  <div id="son">
    <slot name="header"></slot>
    <p>{{myName}}</p>
    <input type="button" value="告诉哥哥我的名字" @click=tellBro>
    <slot name="footer"></slot>
  </div>
</template>

<script>
import eventBus from '../utils/eventBus.js'
export default {
  data () {
    return {
      myName: '女儿组件'
    }
  },
  methods: {
    tellBro () {
      eventBus.$emit('toBro', this.myName)
    }
  }
}

</script>

<style>

</style>
