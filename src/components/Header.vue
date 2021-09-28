<template>
  <header class="header">
    <h1>todos</h1>
    <input type="text" placeholder="what need to be done?" class="new-todo">
  </header>
</template>

<script>
import {Vue, Component, Prop} from "vue-property-decorator";

@Component({
  name: "Header"
})
export default class Header extends Vue {
}
</script>