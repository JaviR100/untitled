<template>
<div>
  <div class="todobody">
    <input type="checkbox">
    {{todo.title}}
  </div>
  <div class="todoaction">
    <button>Eliminar</button>
  </div>
</div>
</template>

<script>
export default {
name: "TodoItem",
  props: ['todo']
}
</script>

<style scoped>
.todo{
  border-bottom: solid 1px crimson;
  padding: 10px;
}
.todo:not(.complete){
  background-color: silver;
}
.complete{
  color: bisque;
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
  padding: 0 10px;
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