<template>
  <div>
    <h1>这里是儿子</h1>
    <h2>{{ wuhu }}</h2>
    <button @click="sonFn">子的按钮</button>
  </div>
</template>

<script lang="ts">

import {Vue, Component, Prop, Emit} from "vue-property-decorator";

@Component({
  name: "Son"
})
export default class Son extends Vue {
  @Prop() wuhu!: string
  /*数据*/
  message = "百度"

  /*方法*/
  @Emit("parentFn")
  sonFn() {
    return 666
  }
}
</script>

<style scoped>

</style>