<template>
  <div>
    <Index/>
  </div>
</template>

<script lang="ts">
import {Component, Vue} from "vue-property-decorator";
import "./assets/todo-mvc.css"
import Index from "@/components/Index.vue";

@Component({
  components: {
    Index
  },
})
export default class App extends Vue {
}
</script>
