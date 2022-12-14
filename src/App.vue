<template>
  <main class="app">
    <section class="greeting">
      <h2 class="title">
        What's up, <span class="name">{{name}}</span>
      </h2>
    </section>
    <section class="create-todo">
      <h3>CREATE A TODO</h3>
      <form @submit.prevent="addTodo">
        <h4>What's on your todo list?</h4>
        <input type="text" placeholder="Make a video" v-model="todo"/>
        <h4>Pick a category</h4>
        <div class="options">
          <label>
            <input type="radio" name="category" value="personal" v-model="category"/>
            <span class="bubble personal"></span>
            <div >Personal</div>
          </label>
           <label>
            <input type="radio" name="category" value="business" v-model="category"/>
            <span class="bubble business"></span>
            <div >Business</div>
          </label>
        </div>
       <input type="submit" value="Add todo">
      </form>
    </section>
  </main>
</template>


<script>
export default {
  data(){
    return {
      todo:'',
      todos:[],
      name:'Vikas',
      category:''
    }
  },
  methods:{
    addTodo(){
      if(this.todo.trim()==''){
        alert('Please enter a todo')
        return
      }
      if(this.category==''){
        alert('Please select a category')
        return
      }
    }
  }
}
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
