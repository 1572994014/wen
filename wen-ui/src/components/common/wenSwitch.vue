<style scoped>
  .checkbox{
    position: relative;
    width: 60px;
    height: 30px;
    border-radius: 20px;
    background: #dcdfe6;
    -webkit-appearance: none;
  }
  .checkbox:before{
    position: absolute;
    margin-left: 2px;
    margin-right: 2px;
    top: 50%;
    transform: translate(0, -50%);
    content: "";
    display: block;
    width: 28px;
    height: 28px;
    background: #fff;
    border-radius: 100%;
    transition: 0.4s
  }
  .checkbox:checked{
    background: #409eff;
  }
  .checkbox:checked:before{
    transform: translate(28px, -50%);
  }
</style>
<template>
<div>
  <input type="checkbox" class="checkbox">
</div>
</template>
