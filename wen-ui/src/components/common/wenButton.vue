<style scoped>
  .button{
    display: inline-block;
    padding: 12px 20px;
    line-height: 1;
    background: #fff;
    border: 1px solid #dcdfe6;
    -webkit-appearance: none;
    text-align: center;
    box-sizing: border-box;
    font-size: 14px;
    border-radius: 4px;
    color: #606266;
  }
  .button:focus, .button:hover {
    color: #409eff;
    border-color: #c6e2ff;
    background-color: #ecf5ff;
  }
</style>
<template>
  <button
  class="button"
  @click="handleClick"
  :autofocus="autofocus"
  >
    <slot></slot>
  </button>
</template>
<script >
export default{
  props: {
    size: String,
    autofocus: Boolean
  },
  methods: {
    handleClick (evt) {
      this.$emit('click', evt)
    }
  }
}
</script>
