<template>
    <div class="input-div">
<input type="text" placeholder="Type your plans" v-model='newTodo' @keyup.enter='addTodo(newTodo)'>

    </div>
</template>

<script lang="ts">

export default {
  name: "InputForm",
  props:['addTodo'],
  data() {
    return {
      newTodo: ""
    };
  },

};
</script>

<style lang="css" scoped>
.input-div {
  width: 100%;
}
input {
  padding:0 10px;
  font-size:18px;
  width: 95%;
  margin:auto;
  height:40px;
}

</style>