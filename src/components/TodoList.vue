<template>
  <section class="main" style="">
    <input type="checkbox" class="toggle-all">
    <ul class="todo-list">
      <Todo/>
      <Todo/>
      <!--      <li class="todo">-->
      <!--        <div class="view">-->
      <!--          <input type="checkbox" class="toggle">-->
      <!--          <label>vue.js</label>-->
      <!--          <button class="destroy"></button>-->
      <!--        </div>-->
      <!--        <input type="text" class="edit" style="display: none;">-->
      <!--      </li>-->
      <!--      <li class="todo completed">-->
      <!--        <div class="view">-->
      <!--          <input type="checkbox" class="toggle">-->
      <!--          <label>react</label>-->
      <!--          <button class="destroy"></button>-->
      <!--        </div>-->
      <!--        <input type="text" class="edit" style="display: none;">-->
      <!--      </li>-->
    </ul>
  </section>
</template>

<script>
import Todo from "@/components/Todo";

export default {
  name: "TodoList",
  components: {Todo}
}
</script>

<style scoped>

</style>