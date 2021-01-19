<template>
  <div>
    <slot></slot>
  </div>
</template>
<script>
export default{
  componentName: 'CheckboxGroup',
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
