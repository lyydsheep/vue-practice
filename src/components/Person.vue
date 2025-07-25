<script setup lang="ts">
import {ref} from 'vue'

const name = ref('张三')
const age = ref(18)
const tel = ref("12306")

function queryTel() {
  alert(tel.value)
}

function changeName() {
  name.value = "zhang-san"
}

function changeAge() {
  age.value = 19
}

</script>

<template>
  <div class="person">
    <h1>姓名：{{ name }}</h1>
    <h1>年龄：{{ age }}</h1>
    <button @click="queryTel">查询电话号码</button>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
  </div>
</template>

<style scoped>
.person {
  width: 100%;
  background: aqua;
}

button {
  margin: 0 10px;
}
</style>