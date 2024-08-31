

<template>

<h1>My Todo App</h1><hr>

  <form @submit.prevent>
    <input type="text" placeholder="new_tasks" v-model="newTasks">
  <button :disabled="newTasks==0" @click="addTasks">+</button>
  </form>

  <!-- Affiche un message lorsque l'utilisateur n'a rien insérer -->
  <div v-if="tasks==0">Insert a task 😢</div>

  <!-- S'affiche lorsque l'utilisateur à commencer à écrire -->
  <div v-else>

    <ul>
       <!-- pour chaque tache dans la liste de tache -->
       <li v-for="task in tasks" :class="{completed: task.completed}"  :id= "{myList: task.name}">

        {{ task.name }}  <!--  Affiche le nom de chaque tache -->
        
        <!-- Est lié à chacune des taches coché grace à v-model  -->
        <input type="checkbox" v-model="task.completed" > 

          <button @click="deleteTasks">Delete</button>
       </li>
    </ul>

    <button @click="displayOrHide"> Display or Hide </button>
    <li v-for="completed in completeds">
      {{ completed.value }}

    </li>

  </div>

  


</template>



<script setup>

import { ref, vModelCheckbox } from 'vue';

//stocker la liste des taches à faire
const tasks=ref([])

//stocker les taches en cours de saisies
const newTasks=ref('')

// Stocker lorsque c'est enlever coché
const completeds=ref([])

// Ajouter une nouvelle tache à la liste des choses à faire
const addTasks=()=>{
   tasks.value.push({
    name:newTasks.value,
    completed:false,
    date:Date.now()
   })
   newTasks.value=''
}

// Supprimer une tache
function deleteTasks(){
     
}

//Enlever un élément et l'afficher dans une autre liste
const displayOrHide=()=>{
  completeds.push(tasks.value)
           
    
   newTasks.value=''
}


</script>


<style >
    
    .completed{
      opacity: 40%;
      text-decoration: line-through;
      
    }

    #myList{
      list-style-type: none;
    }

</style>