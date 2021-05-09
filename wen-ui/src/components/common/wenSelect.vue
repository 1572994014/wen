<style scoped>
  .input-main{
    display: inline-flex;
  }
  input{
    border: 1px solid #dcdfe6;
    box-sizing: border-box;
    height: 40px;
    width: 200px;
    line-height: 40px;
    padding: 0 15px;
    border-radius: 4px;
  }
  input:focus{
    outline: none;
    border-color: #409eff;
  }
</style>
<template>
    <div type="text" class="select">
        <input type="text" placeholder="请选择" readonly="true"  ref="input" @focus="focus" @blur="show = false"/>
        <wen-suggest ref="test" v-show="show"/>
    </div>
</template>
<script>
import wenSuggest from './wenSuggest'
import { createPopper } from '@popperjs/core'
export default{
  components: {
    wenSuggest
  },
  data () {
    return {
      show: false,
      popperJs: null
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScrollx)
    console.log(this.$refs['test'].$el)
    let popcorn = this.$refs['input']
    let tooltip = this.$refs['test'].$el
    console.log(popcorn)
    console.log(tooltip)
    this.popperJs = createPopper(popcorn, tooltip, {
      placement: 'bottom',
      modifiers: [
        {
          name: 'offset',
          options: {
            offset: [0, 8]
          }
        }
      ]
    })
  },
  methods: {
    focus () {
      this.show = true
      this.popperJs.update()
    }
  }
}
</script>
