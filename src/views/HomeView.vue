<!--javascript 代码-->
<script setup>
/**
 * 1. 定义响应式数据
 *    1.1 基础数据类型 使用 ref()
 *    1.2 非基础数据类型 使用 reactive()
 * 2. 文本插值
 *
 * 3. 事件绑定， 比如点击事件
 *
 * 4. 函数定义
 *
 * 5. 修改响应式数据值
 */

import { reactive, ref } from 'vue'

// 定义基础响应式数据
const num = ref(0)

// 定义非基础(对象)数据类型
const userInfo = reactive({
  username: '张三',
  userAge: 18,
  userSex: '女',
})

// 函数定义-箭头函数
const fun1 = () => {
  alert('我被点击了')
}

// 函数定义-关键字function
const increaseNum = function () {
  num.value = num.value + 1
}

const decreaseNum = () => {
  // 将 num 值 + 1
  num.value = num.value - 1
}


const changeAge = function () {
  /**
   * 修改对象的属性值
   * 直接使用属性名进行修改， 不需要在后面添加  value 属性
   */
  userInfo.userAge = 20
}

</script>

<!--html 代码-->
<template>
  <h1>这里是首页</h1>

  <!--文本查值-->
  <span>{{ num }}</span>
  <!--  事件绑定 v-on:click-->
  <button v-on:click="fun1">按钮</button>
  <button v-on:click="increaseNum">增加</button>
  <button v-on:click="decreaseNum">减少</button>
  <hr>
  <table>
    <tr>
      <td>姓名：</td>
      <td> {{ userInfo.username }} </td>
    </tr>
    <tr>
      <td>年龄：</td>
      <td> {{ userInfo.userAge }} </td>
    </tr>
    <tr>
      <td>性别：</td>
      <td> {{ userInfo.userSex }} </td>
    </tr>
  </table>

  <br>
  <button v-on:click="changeAge">修改年龄为 20 岁</button>

</template>

<!--css 代码-->
<style scoped>
h1 {
  color: red;
  font-weight: bold;
}

button {
  margin: 0 20px;
}
</style>
