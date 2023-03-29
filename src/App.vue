<template>
  <div>
    <div class="title">{{ title }}</div>
    <div class="container-to-do">
        <h2>TO DO</h2>
          <input  v-model="addToDo" placeholder="add a thing to do"/>
          <button @click="add" class="click">add</button>
        <ul>
          <li v-for="(todo, index) in todos" :key="todo.id">
            <button @click="change(index)">Change Status</button>
            <span class="to-do-text" >{{ todo.text }}</span>
            <span v-if="todo.done" class="green"> done </span> 
            <span v-else class="red"> not done </span> 
            <button @click="del(index)" class="click">Delete</button>
            
          </li>
        </ul>
    </div>
  </div>
  


</template>

<script>
  export default {
    data(){
      return {
        addToDo: "",
        title: "Hello",
        todos: [
          {id: 1, text: "buy bread", done: true},
          {id: 2, text: "learn go", done: false},
          {id: 3, text: "lern vue", done: true},
          {id: 4, text: "sing jazz", done: false},

        ]

      }
    },
    methods:{
      change(index){
        //console.log(this.todos);
        //console.log(index)
        if(this.todos[index].done == true){
          this.todos[index].done = false;
        }else{
          this.todos[index].done = true;
        }
        
        console.log(this.todos);
      },
      del(index){
        
        this.todos.splice(index, 1);
      },
      add(){
        console.log(this.addToDo);
        this.todos.push({id: 5, text: this.addToDo, done: true})

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
  list-style: none;
  font-weight: bold;
  padding: 10px;
}

span{
  text-align: center;
  text-transform: uppercase;
  padding: 3px;
  display: inline-block;
  width: 100px;


}

.to-do-text{
  font-size: 24px;
  display:inline-block;
  text-transform: uppercase;
  background-color:beige;
  width: 200px;
  margin-right: 15px;
  padding: 5px;

}

.click{
  margin-left: 15px;
  border-radius: 4px;
  padding: 8px;
}

.container-to-do{
  text-align: center;
  width:600px;
  padding:5px;
  background-color: white;
  border: solid rgb(153, 251, 153) 2px;

}

ul{
  padding: 0;
}

button{
  margin-right: 15px;
  border-radius: 4px;
  padding: 8px;
}

    


</style>