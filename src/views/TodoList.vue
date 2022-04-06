<template>
  <div id="root">
    <h1>Todoリスト</h1>
    <form>
      <input name="todo">
    </form>
  </div>
</template>

<script>
  export default {
    name: 'TodoList',
    data() {
      return {
        todo: ''
      }
    }
  }
</script>
