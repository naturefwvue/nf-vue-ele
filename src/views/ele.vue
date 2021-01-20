<template>
  <myInput :meta="meta1"/>
</template>

<script>
import { reactive, ref } from 'vue'
import myInput from '@/components/nf-find/input.vue'

export default {
  name: '',
  components: {
    myInput
  },
  setup () {
    const value = ref('11')
    const meta1 = reactive({
      controlId: 1000,
      colName: 'companyName',
      controlType: 101,
      class: '',
      placeholder: '公司名称',
      title: '公司名称',
      size: 10,
      maxlength: 100,
      optionList: [],
      findKind: '402',
      findKindList: [401, 403, 402, 404, 405, 406],
      tdCount: 1
    })

    return {
      value,
      meta1
    }
  }
}
</script>
