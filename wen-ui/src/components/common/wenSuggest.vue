<style scoped>
  #test{
    position: absolute;
    left: 0;
    top: 0;
  }
</style>
<template>
  <div id="test" :style="{'top': (dom.top + 40 + 'px'), 'left': (dom.left + 'px')}">
    {{dom.top}} px
    {{dom.left}} px
  </div>
</template>
<script>
export default{
  data () {
    return {
      dom: {}
    }
  },
  mounted () {
    document.body.appendChild(this.$el)
    this.dom = this.$parent.$el.getBoundingClientRect()
    console.log(this.$parent.$el)
    window.addEventListener('scroll', () => {
      // this.dom = this.$parent.$el.getBoundingClientRect()
      // console.log(this.$parent.$el.getBoundingClientRect())
    })
  }
}
</script>
