<script setup>
import { ref } from 'vue'

const userName = ref('')
const userPassword = ref('')
const userSex = ref('男')
// const userHobby = ref("乒乓球")
const userHobby = ref([])
</script>

<template>
  <form action="">
    <label for="userName">用户名</label>
    <input id="userName" type="text" v-model="userName" /><span>{{ userName }}</span>
    <hr />
    <label for="userName">密码</label>
    <input id="userName" type="password" v-model="userPassword" /><span>{{ userPassword }}</span>
    <hr />

    <label for="userName">性别</label>

    <input v-model="userSex" value="男" type="radio" name="sex" id="sexMan" /><label for="sexMan"
      >男</label
    >
    <input v-model="userSex" value="女" type="radio" name="sex" id="sexWoman" /><label
      for="sexWoman"
      >女</label
    >
    <input v-model="userSex" value="未知" type="radio" name="sex" id="sexUnknown" /><label
      for="sexUnknown"
      >未知</label
    >
    <br />
    <span>性别： {{ userSex }}</span>
    <hr />

    <!--    <select v-model="userHobby" name="" id="">-->
    <!--      <option value="乒乓球">乒乓球</option>-->
    <!--      <option value="羽毛球">羽毛球</option>-->
    <!--      <option value="足球">足球</option>-->
    <!--    </select>-->

    <!--    <span>{{ userHobby }}</span>-->
    <!--    <hr>-->
    多选框
    <input v-model="userHobby" type="checkbox" name="userHobby" id="足球" value="足球" />
    <label for="足球">足球</label>
    <input v-model="userHobby" type="checkbox" name="userHobby" id="羽毛球" value="羽毛球" />
    <label for="羽毛球">羽毛球</label>
    <input v-model="userHobby" type="checkbox" name="userHobby" id="乒乓球" value="乒乓球" />
    <label for="乒乓球">乒乓球</label>
    <br />
    <span>{{ userHobby }}</span>
    <hr />
  </form>
</template>

<style scoped></style>
