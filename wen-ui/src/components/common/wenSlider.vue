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
  /* .slider-round:hover{
    width: 23px;
    height: 23px;
  } */
  .slider-progress{
    width: 100%;
    height: 5px;
    background: #E4E7ED;
  }
</style>
<template>
  <div class="slider" ref="slider">
    <div class="slider-progress"></div>
    <div class="slider-round" @mouseover="mouseover" @mousedown="mousedown" @mousemove="mousemove" :style="moveButtons"></div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      status: false,
      startX: 0,
      endX: 0,
      left: 0,
      value: 0,
      startValue: 0
    }
  },
  methods: {
    onDragging (e) {
      if (!this.status) return
      this.endX = e.clientX / (500) * 100
      this.value = this.endX - this.startX + this.startValue
      this.value = this.value >= 100 ? 100 : this.value
      this.value = this.value <= 0 ? 0 : this.value
    },
    onDragEnd (e) {
      console.log('end')
      this.status = false
      window.removeEventListener('mousemove', this.onDragging)
      window.removeEventListener('touchmove', this.onDragging)
      window.removeEventListener('mouseup', this.onDragEnd)
      window.removeEventListener('touchend', this.onDragEnd)
      window.removeEventListener('contextmenu', this.onDragEnd)
    },
    mouseStart (e) {
      this.startX = e.clientX / (500) * 100
      this.status = true
    },
    mousedown (e) {
      this.startValue = this.value
      this.mouseStart(e)
      window.addEventListener('mousemove', this.onDragging)
      window.addEventListener('touchmove', this.onDragging)
      window.addEventListener('mouseup', this.onDragEnd)
      window.addEventListener('touchend', this.onDragEnd)
    },
    mousemove (e) {
      if (this.status) {
        this.endX = e.clientX
      }
    },
    mouseover () {
      this.sattus = false
    }
  },
  computed: {
    currentPosition () {
      return `${(this.value)}%`
    },
    moveButtons () {
      return {left: this.currentPosition}
    }
  }
}
</script>
