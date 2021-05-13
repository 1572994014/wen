<style scoped>
</style>
<template>
  <div>
      <wen-switch></wen-switch>
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
    wenSwitch
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
