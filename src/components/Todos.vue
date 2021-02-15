<template>
<div>
  <div v-bind:key="todo.id" v-for="todo in todos">
    <TodoItem v-bind:todo="todo" v-on:delete="$emit('delete', todo.id)"/>
  </div>
</div>
</template>

<script>
import TodoItem from "@/components/TodoItem";
export default {
name: "Todos",
  props : ['todos'],
  components : {
  TodoItem
  }

}
</script>

<style scoped>

</style>