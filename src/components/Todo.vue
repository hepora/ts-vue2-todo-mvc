<template>
  <li class="todo" :class="list.done?'completed':''">
    <div class="view">
      <input type="checkbox" class="toggle" :checked="list.done" @change="changeState">
      <label>{{ list.content }}</label>
      <button class="destroy" @click="deleteOneTodo"></button>
    </div>
    <input type="text" class="edit" style="display: none;">
  </li>
</template>

<script>
import {Component, Emit, Prop, Vue} from "vue-property-decorator";

@Component
export default class Todo extends Vue {
  @Prop() list

  @Emit("deleteOneTodo")
  deleteOneTodo() {
    return this.list.id
  }

  /*改变当前状态*/
  changeState() {
    this.list.done = !this.list.done
  }
}
</script>
