<template>
  <section class="todoapp">
    <Header/>
    <TodoList/>
    <Footer/>
  </section>
</template>

<script lang="ts">
import Header from "@/components/Header";
import TodoList from "@/components/TodoList";
import Footer from "@/components/Footer";

export default {
  name: "Index",
  components: {Footer, TodoList, Header},
  data() {
    return {
      allList: [
        {id: 1, content: "你好啊", done: false},
        {id: 2, content: "芜湖", done: true},
        {id: 3, content: "起飞", done: true},
        {id: 4, content: "厉害了", done: false},
      ]
    }
  }
}
</script>

<style scoped>

</style>