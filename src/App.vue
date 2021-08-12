<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>一个牛人的信息：</h1>
  <h2>姓名：{{person.name}}</h2>
  <h2>年龄：{{person.age}}</h2>
  <h3>工种：{{person.type}}</h3>
  <h3>薪水: {{person.salary}}</h3>
  <h3>工号: {{person.number}}</h3>
  <h3>爱好: {{person.hobby}}</h3>
  <h3>a/b/c/d: {{person.job.a.b.c.d}}</h3>
  <button @click="changeInfo">修改牛人的信息</button>
</template>

<script>
import {reactive } from '@vue/reactivity';
export default {
    name: 'App',
    setup() {
        let person = reactive({
            name: '老苏',
            age: 36,
            job: {
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
            },
            hobby: ['抽烟', '喝酒', '烫头']
        })
        // let number = reactive(666)
        function changeInfo() {
            person.name = '小苏'
            person.age = 18
            person.type = 'UI设计师'
            person.salary = '60K'
            person.number = 999
            person.job.a.b.c.d = 200
            person.hobby[0] = '学习' // vue2.x 不能用索引改
        }
        return {
            person,
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
