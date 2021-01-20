<template>
  <label>
    <input
    v-if="trueLabel || falseLabel"
    type="checkbox"
    v-model="model"
    :disabled="disabled"
    :true-value="trueLabel"
    :false-value="falseLabel"
    :name="name"
    @change="change"
    />
    <input
    v-else
    type="checkbox"
    :value="label"
    v-model="model"
    :disabled="disabled"
    :name="name"
    @change="change"
    />
    <span><slot></slot></span>
  </label>
</template>
<script>
export default{
  props: {
    value: [],
    label: {},
    name: String,
    disabled: {
      type: Boolean,
      default () {
        return false
      }
    },
    trueLabel: [String, Number],
    falseLabel: [String, Number]
  },
  data () {
    return {
      _checkboxGroup: {}
    }
  },
  methods: {
    change () {
    }
  },
  computed: {
    isGroup() {
        let parent = this.$parent;
        while (parent) {
          if (parent.$options.componentName !== 'CheckboxGroup') {
            parent = parent.$parent;
          } else {
            this._checkboxGroup = parent;
            return true;
          }
        }
        return false;
      },
    model: {
      get () {
        return this.isGroup ? this._checkboxGroup.value : this.value
      },
      set (val) {
        if (this.isGroup) {
          let parent = this.$parent
          let name = parent.$options.componentName
          while (parent && (!name || name !== 'CheckboxGroup')) {
            parent = parent.$parent
            if (parent) {
              name = parent.$options.componentName
            }
          }
          if (parent) {
            parent.$emit('input', val)
          }
        } else {
          this.$emit('input', val)
        }
      }
    }
  }
}
</script>
