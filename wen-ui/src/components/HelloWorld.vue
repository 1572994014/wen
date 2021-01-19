<template>
  <div>
    <wen-button>{{checkbox}}</wen-button>
    <div>
      <wen-radio-group v-model="radio">
        <wen-radio label="1" :border="true">选项1</wen-radio>
        <wen-radio label="2">选项2</wen-radio>
      </wen-radio-group>
      <wen-radio-group v-model="radio">
        <wen-radio-button label="1">选项1</wen-radio-button>
        <wen-radio-button label="2">选项2</wen-radio-button>
        <wen-radio-button label="3">选项3</wen-radio-button>
      </wen-radio-group>
      <wen-checkbox v-model="check">{{check}}</wen-checkbox>
      <wen-checkbox-group v-model="checkbox">
        <wen-checkbox label="2">备选项</wen-checkbox>
        <wen-checkbox label="3">备选项</wen-checkbox>
      </wen-checkbox-group>
    </div>
  </div>
</template>
<script>
import wenButton from './common/wenButton'
import wenRadio from './common/wenRadio'
import wenRadioButton from './common/wenRadioButton'
import wenRadioGroup from './common/wenRadioGroup'
import wenCheckbox from './common/wenCheckbox'
import wenCheckboxGroup from './common/wenCheckboxGroup'
export default{
  components: {
    wenButton,
    wenRadio,
    wenRadioGroup,
    wenRadioButton,
    wenCheckbox,
    wenCheckboxGroup
  },
  data () {
    return {
      radio: '',
      radio2: 0,
      check: true,
      checkbox: [2, 3]
    }
  }
}
</script>
