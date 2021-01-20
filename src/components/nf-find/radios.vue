/** 多选组，返回选择的value */
<template>
  <el-radio-group
    name="radioGroup"
    v-model:value="findInfo.value"
    :default-value="modelValue"
  >
    <el-radio checked="true" value="-2" >全部</el-radio>
    <el-radio
      v-for="item in meta.optionList"
      :key="item.value"
      :value="item.value"
    >
        {{item.label}}
    </el-radio>
  </el-radio-group>
</template>

<script>
import manageFind from './nf-manageFind.js'

export default {
  name: 'nf-find-radios',
  model: {
    prop: 'modelValue',
    event: 'input'
  },
  props: {
    modelValue: String,
    meta: {
      type: Object,
      default: () => {
        return {
          controlId: Number, // 编号，区别同一个表单里的其他控件
          controlType: Number, // 用类型编号表示type
          colName: String, // 字段名称
          optionList: Object,
          title: String // 中文名称
        }
      }
    }
  },
  setup (props, conext) {
    // 加载基础的查询管理类
    const { findInfo } = manageFind(props)

    // 默认查询方式
    findInfo.kind = '='
    findInfo.kindkey = 411

    return {
      findInfo
    }
  }
}
</script>
