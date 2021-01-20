<template>
  <el-input
    :id="'id' + meta.controlId"
    :name="'c' + meta.controlId"
    v-model="findInfo.value"
    :placeholder="meta.placeholder"
    :title="meta.title"
    :maxlength="meta.maxlength"
    :autocomplete="meta.autocomplete"
    :key="'ckey_'+meta.controlId"
    :size="findInfo.antSize"
  >
  </el-input>
</template>

<script>
// import { ref, watch, watchEffect, getCurrentInstance } from 'vue'
import { manageFind } from './nf-form.js'

export default {
  name: 'nf-find-input',
  model: {
    prop: 'modelValue',
    event: 'input'
  },
  props: {
    modelValue: Object,
    meta: {
      type: Object,
      default: () => {
        return {
          controlId: Number, // 编号，区别同一个表单里的其他控件
          colName: String, // 字段名称
          controlType: Number, // 用类型编号表示type
          placeholder: String,
          title: String, // 提示信息
          maxlength: Number, // 最大字符数
          autocomplete: { // off
            type: String,
            default: 'on'
          }
        }
      }
    }
  },
  setup (props, conext) {
    // 加载基础的查询管理类
    const { dicFindKind, findInfo, findFun } = manageFind(props)

    // 默认查询方式
    findInfo.kind = '含'
    findInfo.kindkey = 403

    return {
      dicFindKind,
      findInfo,
      findFun
    }
  }
}
</script>
