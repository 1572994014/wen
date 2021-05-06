<style scoped>
  .radio-label{
    display: inline-block;
    margin-right: 30px;
  }
  span{
    font-size: 15px
  }
  .radio-label-border{
    padding: 12px 20px 0 10px;
    height: 40px;
    border: 1px solid #dcdfe6;
    box-sizing: border-box;
    border-radius: 4px;
  }
</style>
<template>
  <label class="radio-label" :class="{'radio-label-border': border}">
    <input
    type="radio"
    v-model="model"
    :value="label"
    :disabled="disabled"
    @change="change"
    />
    <span  class="button"><slot></slot></span>
  </label>
</template>
<script >
export default{
  props: {
    value: {},
    label: {},
    disabled: {
      type: Boolean,
      default () {
        return false
      }
    },
    border: {
      type: Boolean,
      default () {
        return false
      }
    }
  },
  data () {
    return {
      radioGroup: {}
    }
  },
  methods: {
    change () {
      let parent = this.$parent
      let name = parent.$options.componentName
      while (parent && (!name || name !== 'RadioGroup')) {
        parent = parent.$parent
        if (parent) {
          name = parent.$options.componentName
        }
      }
      if (parent) {
        parent.$emit('change', this.label)
      }
    }
  },
  computed: {
    isGroup () {
      let parent = this.$parent
      while (parent) {
        if (parent.$options.componentName !== 'RadioGroup') {
          parent = parent.$parent
        } else {
          this.$set(this, 'radioGroup', parent)
          return true
        }
      }
      return false
    },
    model: {
      get () {
        return this.isGroup ? this.radioGroup.value : this.value
      },
      set (val) {
        this.$emit('input', val)
      }
    }
  }
}
</script>
