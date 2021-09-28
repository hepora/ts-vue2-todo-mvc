<template>
  <li class="todo">
    <div class="view">
      <input type="checkbox" class="toggle">
      <label>vue.js</label>
      <button class="destroy"></button>
    </div>
    <input type="text" class="edit" style="display: none;">
  </li>
</template>

<script>
export default {
  name: "Todo"
}
</script>

<style scoped>

</style>