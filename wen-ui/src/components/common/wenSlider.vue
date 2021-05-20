<style scoped>
  .slider{
    display: flex;
    justify-content: center;
    align-items: center ;
    position: relative;
    width: 500px;
    height: 40px;
  }
  .slider-round{
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 20px;
    height: 20px;
    border-radius: 100%;
    background-color: #fff;
    border: 2px solid #409ef4;
    box-sizing: border-box;
  }
  .slider-round:hover{
    width: 23px;
    height: 23px;
  }
  .slider-progress{
    width: 100%;
    height: 5px;
    background: #E4E7ED;
  }
</style>
<template>
  <div class="slider" ref="slider">
    <div class="slider-progress"></div>
    <div class="slider-round" @mouseover="mouseover" @mousedown="mousedown" @mousemove="mousemove" :style="{'left': left}"></div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      status: false,
      startX: 0,
      endX: 0,
      left: 0
    }
  },
  methods: {
    mousedown (e) {
      this.startX = e.clientX
      this.status = true
      console.log(this.$refs.slider['clientWidth'])
      console.log('鼠标按下')
    },
    mousemove (e) {
      if (this.status) {
        this.endX = e.clientX
        // this.left = (this.endX - this.startX) + 'px'
        // console.log(e.clientX)
        // console.log('鼠标滑动')
      }
    },
    mouseover () {
      this.sattus = false
    }
  }
}
</script>
