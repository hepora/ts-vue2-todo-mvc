<template>
  <section class="main" style="">
    <input type="checkbox" class="toggle-all" :checked="!allDone" @change="changeAllDone">
    <ul class="todo-list">
      <Todo v-for="list in allList" :key="list.id" :list="list"/>
    </ul>
  </section>
</template>

<script lang="ts">
import {Vue, Component, Prop, Emit} from "vue-property-decorator";
import Todo from "@/components/Todo.vue";

@Component({
  components: {Todo},
})
export default class TodoList extends Vue {
  @Prop() allList: any
  @Prop() allDone: any

  @Emit("changeAllDone")
  changeAllDone() {
  }
}
</script>

<style scoped>

</style>