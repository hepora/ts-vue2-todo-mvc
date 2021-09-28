<template>
  <footer class="footer" style="">
    <span class="todo-count"><strong>{{ allDone }}</strong> items left</span>
    <ul class="filters">
      <li><a href="" class="selected">all</a></li>
      <li><a href="" class="">active</a></li>
      <li><a href="" class="">completed</a></li>
    </ul>
    <button class="clear-completed">clear completed</button>
  </footer>
</template>

<script>
import {Vue, Component, Prop} from "vue-property-decorator";

@Component({
  name: "Footer"
})
export default class Footer extends Vue {
  @Prop() allDone
}
</script>

<style scoped>

</style>