<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>一个牛人的信息：</h1>
  <h2>姓名：{{name}}</h2>
  <h2>年龄：{{age}}</h2>
  <h3>工种：{{job.type}}</h3>
  <h3>薪水: {{job.salary}}</h3>
  <h3>工号: {{job.number}}</h3>
  <h3>爱好: {{hobby}}</h3>
  <h3>a/b/c/d: {{job.a.b.c.d}}</h3>
  <button @click="changeInfo">修改牛人的信息</button>
</template>

<script>
import { ref, reactive } from '@vue/reactivity';
export default {
    name: 'App',
    setup() {
        let age = ref(36);
        let name = ref('老苏');
        let job = reactive({
            type: '前端工程师',
            salary: '30K',
            number: 666,
            a: {
                b: {
                    c: {
                        d: 100
                    }
                }
            }
        })
        let hobby = reactive(['抽烟', '喝酒', '烫头'])
        // let number = reactive(666)
        function changeInfo() {
            // console.log(number)
            // name.value = '小苏'
            // age.value = 18
            // job.type = 'UI设计师'
            // job.salary = '60K'
            // // console.log(name, age)
            // job.number = 999
            // job.a.b.c.d = 200
            hobby[0] = '学习' // vue 不能用索引改
        }
        return {
            age,
            name,
            job,
            hobby,
            changeInfo,
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
