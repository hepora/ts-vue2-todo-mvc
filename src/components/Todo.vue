<template>
  <li class="todo" :class="list.done?'completed':''">
    <div class="view">
      <input type="checkbox" class="toggle" :checked="list.done" @change="changeState">
      <label>{{ list.content }}</label>
      <button class="destroy"></button>
    </div>
    <input type="text" class="edit" style="display: none;">
  </li>
</template>

<script>
import {Component, Prop, Vue} from "vue-property-decorator";

@Component({
  name: "Todo"
})
export default class Todo extends Vue {
  @Prop() list

  changeState() {
    this.list.done = !this.list.done
  }
}
</script>

<style scoped>

</style>