<template>
  <div class='app'>
    
    <InputForm v-bind:addTodo='addTodo'/>
    <Todos v-bind:todos="todos"
     v-bind:deleteItem="deleteItem"
      v-bind:completed="completed"/>
    
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

import InputForm from "./components/InputForm";
import Todos from "./components/Todos";

export default {
  name: "app",
  components: {
    Todos,
    InputForm
  },
  data() {
    return {
      todos: []
    };
  },
  async created() {
    try {
      const res = await axios.get("https://jsonplaceholder.typicode.com/todos");
      this.todos = res.data;
    } catch (error) {
      console.error(error);
    }
  },
  methods: {
    addTodo(input) {
      const arr = this.todos;
      arr.unshift({
        userId: 11,
        id: arr.length + 1,
        title: input,
        completed: false
      });
      this.todos = arr;
    },
    deleteItem(idToDelete) {
      const arr = this.todos.filter(item => item.id != idToDelete);

      this.todos = arr;
    },
    completed(idHandle) {
      this.todos[idHandle - 1].completed= !this.todos[idHandle - 1].completed
      console.log(this.todos[idHandle - 1].completed)
    }
  }
};
</script>




<style>
.app {
  font-size: 18px;
  box-sizing: border-box;
  overflow-x: hidden;
  font-family: Arial, sans-serif;

  color: #000000;
  margin-top: 60px;
  max-width: 1100px;
  margin: auto;
}
</style>
