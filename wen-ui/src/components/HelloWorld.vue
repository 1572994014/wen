<style scoped>
</style>
<template>
  <div>
      <wen-switch></wen-switch>
      <wen-slider></wen-slider>
      <wen-time-picker></wen-time-picker>
  </div>
</template>
<script>
import wenButton from './common/wenButton'
import wenRadio from './common/wenRadio'
import wenRadioButton from './common/wenRadioButton'
import wenRadioGroup from './common/wenRadioGroup'
import wenCheckbox from './common/wenCheckbox'
import wenCheckboxGroup from './common/wenCheckboxGroup'
import wenInput from './common/wenInput'
import wenSelect from './common/wenSelect'
import wenSwitch from './common/wenSwitch'
import wenSlider from './common/wenSlider'
import wenTimePicker from './common/wenTimePicker'
export default{
  components: {
    wenButton,
    wenRadio,
    wenRadioGroup,
    wenRadioButton,
    wenCheckbox,
    wenCheckboxGroup,
    wenInput,
    wenSelect,
    wenSwitch,
    wenSlider,
    wenTimePicker
  },
  data () {
    return {
      radio: '',
      radio2: 0,
      check: true,
      checkbox: []
    }
  }
}
</script>
