/** 下拉列表框，多选的那个再考虑考虑 */
<template>
  <el-select :id="'c'+meta.controlId"
    style="width:98%"
    v-model:value="findInfo.value"
    :name="'c'+meta.controlId"
    :placeholder="meta.placeholder"
    :size="findInfo.antSize"
  >
      <el-select-option value="-2">全部{{meta.placeholder}}</el-select-option>
      <el-select-option v-for="(item,index) in meta.optionList"
        :key="index"
        :value="item.value" >
          {{item.title}}
      </el-select-option>
    </el-select>
</template>

<script>
import manageFind from './nf-manageFind.js'

export default {
  name: 'nf-find-select',
  model: {
    prop: 'modelValue',
    event: 'change'
  },
  props: {
    modelValue: String,
    meta: {
      type: Object,
      default: () => {
        return {
          controlId: Number, // 编号，区别同一个表单里的其他控件
          controlType: Number, // 用类型编号表示type
          colName: [String, Object], // 字段名称
          placeholder: String,
          optionList: Object,
          title: String // 中文名称
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
