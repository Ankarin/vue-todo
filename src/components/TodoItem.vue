<template>
    <div class='todo-item'>
 <i v-on:click='deleteItem(todo.id)' class="fas fa-times"></i>
<p >{{todo.title}}</p>
<div class="change">
 <div class='check-div'>
  <input type='checkbox' v-model='checked' v-on:click="completed(todo.id)"/>
  </div>
  
</div>

    </div>
</template>

<script >
    

    export default {
        name:'TodoItem',
        props:["todo", 'deleteItem', "completed"],
        data() {
    return {
      checked: this.todo.completed
    };
  },
        
    };
    
</script>

<style scoped>
 p{
   padding-left:10px;
   width:100%;
    text-align:left !important;
  }
.todo-item {
  padding:0 !important;
 
  display:flex;
  align-items:center;
  justify-content:space-between;
  
    background: #ffffff;
    padding: 10px;
    
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
.change {
  height:100%;
  display:flex;
  flex-direction:column;
  align-items: center;
  justify-items:center;
  
  
}
.fas {
  color:red;
  cursor:pointer;
  font-size:28px;
}
input{
  
  color:red;
  cursor:pointer;
height:22px;
width:22px;
}
  
.check-div {
  padding:0;
  
}

</style>