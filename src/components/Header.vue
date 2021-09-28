<template>
  <header class="header">
    <h1>todos</h1>
    <input type="text" v-model="content" @keyup.enter="addOneTodo" placeholder="what need to be done?" class="new-todo">
  </header>
</template>

<script>
import {Vue, Component, Prop, Emit} from "vue-property-decorator";

@Component({
  name: "Header"
})
export default class Header extends Vue {
  content = ""

  @Emit("addOneTodo")
  addOneTodo() {
    let temp = this.content
    this.content = ""
    return temp
  }
}
</script>