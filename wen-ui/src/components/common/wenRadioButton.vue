<style scoped>
  .radio-button{
    position: relative;
    display: inline-block;
  }
  .radio-button input{
    position: absolute;
    z-index: -1;
  }
  .radio-button .button{
    display: inline-block;
    padding: 12px 20px;
    line-height: 1;
    background: #fff;
    border: 1px solid #dcdfe6;
    -webkit-appearance: none;
    text-align: center;
    box-sizing: border-box;
    font-size: 14px;
    color: #606266;
  }
  input:checked + .button{
    background: #409eff;
    color: #fff;
  }
</style>
<template>
  <label class="radio-button">
    <input
    type="radio"
    v-model="model"
    :value="label"
    :disabled="disabled"
    @change="change"
    />
    <span class="button"><slot></slot></span>
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
          this.set(this, 'radioGroup', parent)
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
