<template>
 <div id="add_container">
   <form action="" @submit="addTodo">
     <label>
       <input type="text" v-model="title">
     </label>
   </form>
 </div>
</template>

<script>
import {uuid} from 'vue-uuid' //Para crear un id aleatorio
export default {
name: "TodosAdd",
  data(){
    return {
      title: ''
            }
  },
  methods:{
      addTodo(nuevo)
              {
                nuevo.preventDefault()
                const addarray = {
                  id : uuid.v4(),
                  title: this.title,
                  complete: false
                }
                this.title = ""
                this.$emit('add',addarray)
              }

  }
}
</script>

<style scoped>
#add_container{
  padding: 19px;
}
input {
  padding: 10px;
  outline: none;
  border: solid darkolivegreen;
  width: 100%;
}
</style>