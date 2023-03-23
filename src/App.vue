<template>
  <div>
    <div class="title">{{ title }}</div>
    <div>
        <h2>TO DO</h2>
        <ul>
          <li v-for="(todo, index) in todos" :key="todo.id">{{ todo.text }}
            <span v-if="todo.done" class="green"> done </span> 
            <span v-else class="red"> not done </span> 
            <button @click="change(index)">Change Status</button>
          </li>
        </ul>
    </div>
  </div>
  


</template>

<script>
  export default {
    data(){
      return {
        title: "Hello",
        todos: [
          {id: 1, text: "yey", done: true},
          {id: 2, text: "you", done: false},
          {id: 3, text: "yes", done: true},
          {id: 4, text: "yon", done: false},

        ]

      }
    },
    methods:{
      change(index){
        console.log(this.todos);
        console.log(index)
        if(this.todos[index].done == true){
          this.todos[index].done = false;
        }else{
          this.todos[index].done = true;
        }
        
        console.log(this.todos);
      }
    }

  }

</script>

<style scoped>
.title{
    text-align: center;
    font-size: 50px;
    width: 400px;
    margin: auto;
  }

.red{
    background-color: red;
    color: white;
    

}

.green{
    background-color: green;
    color: white;
   
}

li{
  font-weight: bold;
  padding: 10px;
}

span{
  border-radius: 6px 6px;
  padding: 3px;
}

    


</style>