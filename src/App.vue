<template>
  <div>
    <div id="header"></div>
    <div id="main-container">
      <h2>Lista de Tareas</h2>
      <TodosAdd v-on:add="addTodo"/>
      <Todos v-bind:todos="copyTodos" v-on:delete="deleter"/>
    </div>
  </div>
</template>

<script>
import Todos from "@/components/Todos";
import TodosAdd from "./components/TodosAdd";

export default {
  name: 'App',
  components: {
    Todos, TodosAdd
  },
  data () {
      return {
        todos : [
          {
            id : 0,
            title : 'Comprar la cena',
            complete : false
          },
          {
            id : 1,
            title : 'Recargar la tarjeta del metro bus',
            complete : false
          },
          {
            id : 2,
            title : 'Sacar a los perros cuando llegas a la casa',
            complete : false
          },
          {
            id : 3,
            title : 'Sacar dinero del cajero para lavar la ropa',
            complete : true
          }
        ],
        copyTodos : []

      }

  },
  created() {
    this.copyTodos = [...this.todos]
  },
  methods: {
    deleter(id){
      this.todos = this.todos.filter(todo => todo.id != id)
      this.copyTodos = [...this.todos]
    },
    addTodo(todo){
      this.todos.push(todo)
      this.copyTodos = [...this.todos]
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}
body{
  font-family: Bitstream Charter, Garuda, sans-serif;
  font-size: 19px;
  padding: 0;
  margin: 0;
}
#main-container {
  border: solid 1px silver;
  width: 600px;
  margin: 100px auto;
}
#header{
  background: crimson;
  padding: 10px;
}
h2{
  padding: 0 10px;
}
</style>
