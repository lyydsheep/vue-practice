<template>
  <div class="person">
    <h1>姓名：{{ name }}</h1>
    <h1>年龄：{{ age }}</h1>
    <button @click="queryTel">查询电话号码</button>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>

    <h1>汽车的名字：{{ car.carName }}， 价格：{{ car.carPrice }}</h1>
    <button @click="changePrice">修改汽车价格</button>
    <ul>
      <li v-for="game in games">
        游戏名称：{{ game.name }}， 价格：{{ game.price }}
      </li>
    </ul>
    <button @click="changeFirst">修改第一个游戏</button>
  </div>
</template>


<script setup lang="ts">
import {reactive, ref} from 'vue'

const name = ref('张三')
const age = ref(18)
const tel = ref("12306")
const car = reactive({carName: "兰博基尼", carPrice: 100})
const games = reactive([{name: "LOL", price: 10}, {name: "DNF", price: 20}, {name: "QQ", price: 30}])

function changeFirst() {
  games[0].name = "WX"
}

function queryTel() {
  alert(tel.value)
}

function changeName() {
  name.value = "zhang-san"
}

function changeAge() {
  age.value = 19
}

function changePrice() {
  car.carPrice += 10
}

</script>


<style scoped>
.person {
  width: 100%;
  background: aqua;
}

button {
  margin: 0 10px;
}
</style>