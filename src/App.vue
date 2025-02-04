<script setup>
import {ref} from 'vue'

const myArray = ref([])
const name = ref('')
const input_content = ref('')
const input_catagory = ref(null)

const addTodo = () =>{
  if(input_content.value.trim() === '' || input_catagory.value == null){

    return
  }

  myArray.value.push({

    content: input_content.value,
    catagory: input_catagory.value,
  })


  input_content.value = ''
  input_catagory.value = null

}
</script>

<template>

<main class="app">

<section class="greeting">
<h2 class="title">
welcome back, <input type="text" placeholder="Enter Name" v-model="name">

</h2>
</section>

<section class="create-todo">
<h3>CREATE A TO DO LIST</h3>
<form @submit.prevent = "addTodo">
<h4>What's on your to do list </h4>
<input type="text" placeholder="e.g., Make a Video" v-model="input_content"/>


  <h4>Pick a Catagory</h4>
    <div class ="options">
      <label>
        <input type="radio" name="catagory" value="business" v-model="input_catagory">
        <span class="bubble business"></span>
        <div>Business</div>
      </label>
      <label>
        <input type="radio" name="catagory" value="personal" v-model="input_catagory">
        <span class="bubble personal"></span>
        <div>Personal</div>
      </label>
    </div>
    <input type="submit" value="Add To Do"/>
  
</form>
</section>

<section class="todo-list">

</section>




</main>

</template>


