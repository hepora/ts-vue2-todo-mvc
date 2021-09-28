<template>
  <footer class="footer" style="">
    <span class="todo-count"><strong>{{ allDone }}</strong> items left</span>
    <ul class="filters">
      <li><a href="" @click.prevent="changeShowList('all')" :class="showWhat==='all'?'selected':''">all</a></li>
      <li><a href="" @click.prevent="changeShowList('active')" :class="showWhat==='active'?'selected':''">active</a></li>
      <li><a href="" @click.prevent="changeShowList('done')" :class="showWhat==='completed'?'selected':''">completed</a></li>
    </ul>
    <button class="clear-completed">clear completed</button>
  </footer>
</template>

<script>
import {Vue, Component, Prop, Emit} from "vue-property-decorator";

@Component({
  name: "Footer"
})
export default class Footer extends Vue {
  @Prop() allDone
  @Prop() showWhat

  @Emit("changeShowList")
  changeShowList(what) {
    return what
  }
}
</script>
