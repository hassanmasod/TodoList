<template>

    
    <div class="todo-list">
        <h1>Todo-List</h1>
    
        <input  class="text-field" type="text" @change="addToList" v-model="text" />
    
        <ul>
          <li v-for="(item, index) in list" :key="index">
            <span @click="toggleCheck(item)">
              <input type="checkbox" :checked="item.done" />
              <span :class="{ done: item.done }">{{ item.label }}</span>
            </span>
            <button @click="deleteFromList(index)">Delete</button>
          </li>
        </ul>
      </div>

   
</template>
<script>
export default {
    name: 'FirstPage',
    
    data() {
    return {
      list: [],
      text: ""
    };
  },

  methods: {
    addToList() {
      this.list.unshift({ label: this.text, done: false });
    
      this.text = "";
    },
    deleteFromList(index) {
      this.list.splice(index, 1);
    
    },
    
    toggleCheck(item) {
      item.done = !item.done;
    
    }
  }



}

</script>

<style scoped>
input
{
    outline: none;
    font-weight: bold;
    padding-left: 10px;
}
button{
    background-color: rgb(3, 12, 145);
    border-radius: 5px;
    color: aliceblue;
    width: 100px;
    
}

.todo-list {
    max-width: 500px;
    margin: auto;
    margin-top: 15%;
  }
  
  h1 {
    text-align: center;
    color : rgb(9, 72, 247);
    text-shadow: 2px 2px 8px #1fb6e4;
    margin-bottom: 20px;
  }
  
  .text-field {
    width: 100%;
    height: 35px;
    margin-bottom: 15px;
    background-color: rgb(61, 206, 250);
    border-radius: 5px;
    box-shadow: 5px 10px 18px rgb(1, 163, 238);
   margin-bottom: 30px;
   border: none;

  }
  
  ul {
    list-style: none;
    padding: 0;
    
  }
  
  li {
    display: flex;
    justify-content: space-between;
   
  }
  
  .done {
    text-decoration: none;

  }

</style>