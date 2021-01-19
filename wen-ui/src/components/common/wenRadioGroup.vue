<style scoped>
  .radio-group{
    line-height: 1;
    font-size: 0;
  }
</style>
<template>
  <div class="radio-group">
    <slot></slot>
  </div>
</template>
<script>
export default{
  props: {
    value: {}
  },
  componentName: 'RadioGroup',
  computed: {
    model: {
      get () {
        return this.value
      },
      set (val) {
        this.$emit('input', val)
      }
    }
  },
  created () {
    this.$on('change', value => {
      this.$emit('input', value)
    })
  }
}
</script>
