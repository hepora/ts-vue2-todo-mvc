<template>
  <div class="hello">
    <input v-model="str">
    <h1>{{ theStr }}</h1>
    <h1>{{ message }}</h1>
    <button @click="getSon">我是你爹</button>
    <Son :title="message" :wuhu="str" @parentFn="parentFn"/>
  </div>
</template>

<script lang="ts">
import {Component, Prop, Vue, Watch} from "vue-property-decorator";
import Son from "@/components/Son.vue";

@Component({
  components: {Son}
})
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
  /*数据绑定*/
  str = "你好啊";
  message = "我不好";
  obj = {
    name: "哈哈哈啊",
    age: 118
  }

  /*访问器，就是计算属性*/
  get theStr() {
    console.log("theStr触发了");
    return this.str.split("").reverse().join("");
  }

  /*方法*/
  getSon() {
    console.log("窝嫩叠窝嫩叠窝嫩叠窝嫩叠窝嫩叠窝嫩叠窝嫩叠窝嫩叠窝嫩叠");
  }

  parentFn(data: any) {
    console.log(data)
    this.str += "窝嫩叠"
  }

  /*Watch，监听*/
  @Watch("str")
  strChange(newValue: string, oldValue: string) {
    console.log(newValue)
    console.log(oldValue)
  }

  @Watch("obj", {deep: true})
  objChange(newValue: any, oldValue: any) {
    console.log(newValue)
    console.log(oldValue)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
.hello
  background-color: #41b883
</style>
