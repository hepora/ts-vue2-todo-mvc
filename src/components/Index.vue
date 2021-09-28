<template>
  <section class="todoapp">
    <Header/>
    <TodoList
        :allList="allList"
        :allDone="allDone"
        @changeAllDone="changeAllDone"
        @deleteOneTodo="deleteOneTodo"
    />
    <Footer :allDone="allDone"/>
  </section>
</template>

<script lang="ts">
import Header from "@/components/Header.vue";
import TodoList from "@/components/TodoList.vue";
import Footer from "@/components/Footer.vue";
import {Component, Vue} from "vue-property-decorator";

@Component({
  name: "Index",
  components: {Footer, TodoList, Header}
})
export default class Index extends Vue {
  allList = [
    {id: 1, content: "你好啊", done: false},
    {id: 2, content: "芜湖", done: true},
    {id: 3, content: "起飞", done: true},
    {id: 4, content: "厉害了", done: false},
  ]

  /*方法*/

  /*改变全部状态*/
  changeAllDone() {
    if (this.allDone) {
      this.allList.forEach(item => item.done = true)
    } else {
      this.allList.forEach(item => item.done = false)
    }
  }

  /*删除一条数据*/
  deleteOneTodo(id) {
    console.log(this.allList.findIndex(item => item.id === id));
  }

  /*计算属性*/
  get allDone() {
    /*遍历寻找未完成的，然后将未完成的数量返回*/
    return this.allList.filter(item => !item.done).length
  }

}
</script>

<style scoped>

</style>