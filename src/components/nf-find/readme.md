# 查询控件和查询子控件

使用vue3.0的方式实现

# 功能
## 快速查询
可以把常用的查询条件放在第一行，便于直接使用

## 个性化查询
用户可以把自己常用的查询条件作为查询方案，需要是快速召唤

## 全部查询
显示全部的查询条件，选择后可以在快捷里显示，方便后续查询

## 更换查询方式
可以精确查询、模糊查询、范围查询等

## 切换日期格式
日期控件可以切换各种形式，比如年月日、年月、年周、日期+时间、时间，可以等于日期，也可以按照范围查询。

# 使用方法
需要设置meta

## meta格式

# 返回值的格式
数组对象方式
第一个是查询方法，后面的是查询关键字

# 设计思路
先封装基础控件，然后在做一个整合的控件

## 子控件
分为文本、数字、日期、选择（多选、单选、下拉）