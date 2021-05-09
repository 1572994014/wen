<style scoped>
  .suggest-controller{
    left: 0;
    padding: 10px;
  }
  .suggest-border{
    border: 1px solid #dcdfe6;
    box-sizing: border-box;
    width: 200px;
    line-height: 40px;
    border-radius: 4px;
    background-color: #FFFFFF;
  }
  .suggest-main{
    padding: 0 15px;
  }
  .suggest-main:hover{
    background-color: #F5F7FA;
  }
  /* .suggest-border::after{
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    transform: translateY(-100%);
    border-left: 5px solid transparent;
    border-right: 5px solid transparent;
    border-bottom: 10px solid #fff;
  } */
</style>
<template>
  <div class="suggest-controller">
    <div class="suggest-border">
      <div v-for="o in options" :key="o.value" class="suggest-main">{{o.label}}</div>
    </div>
  </div>
</template>
<script>
export default{
  data () {
    return {
      dom: {},
      options: [{
        value: '选项1',
        label: '黄金糕'
      }, {
        value: '选项2',
        label: '双皮奶'
      }, {
        value: '选项3',
        label: '蚵仔煎'
      }, {
        value: '选项4',
        label: '龙须面'
      }, {
        value: '选项5',
        label: '北京烤鸭'
      }]
    }
  },
  mounted () {
    document.body.appendChild(this.$el)
    // this.dom = this.$parent.$el.getBoundingClientRect()
    // console.log(this.$parent.$el)
    // window.addEventListener('scroll', () => {
    //   this.dom = this.$parent.$el.getBoundingClientRect()
    //  console.log(this.$parent.$el.getBoundingClientRect())
    // })
  }
}
</script>
