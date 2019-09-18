<template>
  <div>
    
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" v-bind:completed="completed" v-bind:deleteItem='deleteItem'/>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  components:{
      TodoItem
  },
  props: ["todos", "deleteItem", "completed"]
};
</script>

<style scoped>
</style>