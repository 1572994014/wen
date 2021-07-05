<style scoped>
  .input-main{
    display: inline-flex;
  }
  input{
    border: 1px solid #dcdfe6;
    box-sizing: border-box;
    height: 40px;
    width: 200px;
    line-height: 40px;
    padding: 0 15px;
    border-radius: 4px;
  }
  input:focus{
    outline: none;
    border-color: #409eff;
  }
</style>
<template>
  <div class="input-main">
    <input type="text" ref="input">
    <wen-suggest ref="test"/>
  </div>
</template>
<script>
import wenSuggest from './wenSuggest'
import { createPopper } from '@popperjs/core'
export default{
  components: {
    wenSuggest
  },
  mounted () {
    window.addEventListener('scroll', this.handleScrollx)
    console.log(this.$refs['test'].$el)
    let popcorn = this.$refs['input']
    let tooltip = this.$refs['test'].$el
    console.log(popcorn)
    console.log(tooltip)
    createPopper(popcorn, tooltip)
  },
  methods: {
  }
}
</script>
