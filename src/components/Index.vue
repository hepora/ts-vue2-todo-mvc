<template>
  <section class="todoapp">
    <Header/>
    <TodoList
        :showList="showList"
        :allDone="allDone"
        @changeAllDone="changeAllDone"
        @deleteOneTodo="deleteOneTodo"
    />
    <Footer :allDone="allDone" :showWhat="showWhat" @changeShowList="changeShowList"/>
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
  /*所有数据*/
  allList = [
    {id: 1, content: "你好啊", done: false},
    {id: 2, content: "芜湖", done: true},
    {id: 3, content: "起飞", done: true},
    {id: 4, content: "厉害了", done: false},
  ]
  /*要展示的是啥*/
  showWhat: string = "all"

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
  deleteOneTodo(id: number) {
    this.allList.splice(this.allList.findIndex(item => item.id === id), 1)
  }

  /*改变显示列表*/
  changeShowList(what: string) {
    this.showWhat = what
  }

  /*计算属性*/
  get allDone() {
    /*遍历寻找未完成的，然后将未完成的数量返回*/
    return this.allList.filter(item => !item.done).length
  }

  /*要展示的列表*/
  get showList() {
    switch (this.showWhat) {
      case "all":
        return this.allList
      case "active":
        return this.allList.filter(item => !item.done)
      case "done":
        return this.allList.filter(item => item.done)
      default:
        return this.allList
    }
  }
}
</script>
