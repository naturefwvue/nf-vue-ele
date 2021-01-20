<template>
  <myInput :meta="meta[1000]"/>
  <number :meta="meta[1001]"/><br>
  <cascaders :meta="meta[1013]"/><br>
  <checks :meta="meta[1012]"/><br>
  <datetime :meta="meta[1009]"/><br>
  <nftime :meta="meta[1013]"/><br>
  <radios :meta="meta[1011]"/><br>
  <selects :meta="meta[1008]"/><br>
</template>

<script>
import { reactive, ref } from 'vue'
import myInput from '@/components/nf-find/input.vue'
import number from '@/components/nf-find/number.vue'
import cascaders from '@/components/nf-find/cascaders.vue'
import checks from '@/components/nf-find/checks.vue'
import datetime from '@/components/nf-find/datetime.vue'
import nftime from '@/components/nf-find/time.vue'
import radios from '@/components/nf-find/radios.vue'
import selects from '@/components/nf-find/select.vue'

export default {
  name: '',
  components: {
    number,
    cascaders,
    checks,
    datetime,
    nftime,
    radios,
    selects,
    myInput
  },
  setup () {
    const value = ref('11')
    const json = require('./json/FindDemo.json')

    const meta = reactive(json.company.findItem)
    console.log(meta)

    return {
      value,
      meta
    }
  }
}
</script>
