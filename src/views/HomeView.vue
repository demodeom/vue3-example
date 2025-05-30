<!--javascript 代码-->
<script setup>
/**
 * 复杂数据类型渲染：
 *
 * 1. 数组
 */

import { reactive } from 'vue'

const jobs = reactive(['吃饭', '睡觉', '打豆豆'])

const users = reactive([
  {
    id: '2020120101',
    name: '用户1',
    sex: '保密',
  },
  {
    id: '2020120102',
    name: '用户2',
    sex: '男',
  },
  {
    id: '2020120103',
    name: '用户3',
    sex: '女',
  },
])
</script>

<!--html 代码-->
<template>
  <ul>
    <li v-for="(item, index) in jobs" v-bind:key="index">{{ index }} - {{ item }}</li>
  </ul>

  <table>
    <thead>
      <tr>
        <th>学号</th>
        <th>姓名</th>
        <th>性别</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(user, index) in users" v-bind:key="index">
        <td>{{ user.id }}</td>
        <td>{{ user.name }}</td>
        <td>{{ user.sex }}</td>
      </tr>
    </tbody>
  </table>
  <hr>
  <table>
    <thead>
      <tr>
        <th>学号</th>
        <th>姓名</th>
        <th>性别</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(user, index) in users" v-bind:key="index">
        <td>{{ user.id }}</td>
        <td>{{ user.name }}</td>

        <td v-if="user.sex === '男'" style="color: blue">{{ user.sex }}</td>
        <td v-else-if="user.sex === '女'" style="color: red">{{ user.sex }}</td>
        <td v-else>{{ user.sex }}</td>
      </tr>
    </tbody>
  </table>
</template>

<!--css 代码-->
<style scoped>
table {
  width: 800px;
  text-align: center;
  border-spacing: 0;
}

th,
td {
  border: 1px solid black;
}
</style>
