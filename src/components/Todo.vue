<template>
  <li class="todo" :class="list.done?'completed':''">
    <div class="view">
      <input type="checkbox" class="toggle" :checked="list.done" @change="changeState">
      <label
          :style="edit?{display:'none'}:{display: 'block'}"
          @dblclick="changeEdit"
      >{{ list.content }}</label>
      <button class="destroy" @click="deleteOneTodo"></button>
    </div>
    <input
        type="text"
        v-model="list.content"
        class="edit"
        :style="edit?{display:'block'}:{display:'none'}"
        @keyup.enter="changeEdit"
    >
  </li>
</template>

<script>
import {Component, Emit, Prop, Vue} from "vue-property-decorator";

@Component
export default class Todo extends Vue {
  edit = false

  @Prop() list

  @Emit("deleteOneTodo")
  deleteOneTodo() {
    return this.list.id
  }

  /*改变当前状态*/
  changeState() {
    this.list.done = !this.list.done
  }

  /*当前是否编辑*/
  changeEdit() {
    if (this.edit) {
      this.list.content = this.list.content.trim()
    }
    if (this.list.content === "") {
      this.deleteOneTodo()
    }
    this.edit = !this.edit
  }

}
</script>
