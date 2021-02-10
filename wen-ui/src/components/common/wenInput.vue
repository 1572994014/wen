<style scoped>
  input{
    border: 1px solid #dcdfe6;
    box-sizing: border-box;
    height: 40px;
    line-height: 40px;
    padding: 0 15px;
    border-radius: 4px;
  }
</style>
<template>
  <label>
    <input type="text">
    <wen-suggest/>
  </label>
</template>
<script>
import wenSuggest from './wenSuggest'
export default{
  components: {
    wenSuggest
  },
  mounted () {
    window.addEventListener('scroll', this.handleScrollx)
  },
  methods: {
    handleScrollx () {
      // console.log(this.$el.getBoundingClientRect())
    }
  }
}
</script>
