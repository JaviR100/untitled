<template>
<div class="todo" v-bind:class="{complete: todo.complete}">
  <div class="todobody" >
    <input type="checkbox" v-bind:checked="todo.complete? 'checked': ''" v-on:change="checkTodo">
    {{todo.title}}
  </div>
  <div class="todoaction">
    <button @click="$emit('delete',todo.id)">Eliminar</button>
  </div>
</div>
</template>

<script>
export default {
name: "TodoItem",
  props: ['todo'],
  methods : {
  checkTodo()
  {
    this.todo.complete = !this.todo.complete
  }
  }
}
</script>

<style scoped>
.todo{
  border-bottom: solid 1px crimson;
  padding: 10px;
}
.todo:not(.complete){
  background-color: white;
}
.complete{
  color: darkred;
  text-decoration: line-through;
}
.complete .todobody {
  text-decoration: line-through;
}
.todobody, .todoaction {
  display: inline-block;
  vertical-align: top;
}
.todobody{
  width: 85%;
}
.todoaction{
  padding:  10px;
  width: 10%;
}
button{
  border: none;
  border-radius: 10px;
  padding: 10px;
  background-color: crimson;
  color: black;
}
button:hover{
  background-color: brown;
  color: white;
}
</style>