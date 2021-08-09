<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>一个牛人的信息：</h1>
  <h2>姓名：{{name}}</h2>
  <h2>年龄：{{age}}</h2>
  <h3>工种：{{job.type}}</h3>
  <h3>薪水: {{job.salary}}</h3>
  <button @click="changeInfo">修改牛人的信息</button>
</template>

<script>
import { ref } from '@vue/reactivity';
export default {
    name: 'App',
    setup() {
        let age = ref(36);
        let name = ref('老苏');
        let job = ref({
            type: '前端工程师',
            salary: '30K'
        })
        function changeInfo() {
            name.value = '小苏'
            age.value = 18
            job.value.type = 'UI设计师'
            job.value.salary = '60K'
            console.log(name, age)
        }
        return {
            age,
            name,
            job,
            changeInfo
        }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
