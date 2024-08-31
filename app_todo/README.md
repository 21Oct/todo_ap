Exerice

<!-- <template>
    
 <h1>My Todo App </h1><hr>

 <form action="" @submit.prevent="addTask">
   
     <input type="text" placeholder="new_task" v-model="newTasks"/>
     <button :disabled= "newTasks==0" >+</button>

 </form>
 <!-- ce texte disparait lorsque l'utilisateur insert quelque chose -->
 <div v-if= "tasks.length==0">Insert a task😢</div>

 <div v-else>

 <ul>
   <fieldset>
   <!-- créer une nouvelle tache pour chaque 'task' dans 'tasks' -->
    <li v-for="task in tasks" @change="addcompleteds">
    {{ task.title}}
    <label>
    <input type="checkbox" v-model-checkbox="task.completed">
    <button @click="deleteTasks">Delete</button>
    </label>
    </li>
   
   </fieldset>

  </ul>
 </div>
  <button @click="displayOrHide"> Display or Hide </button>
   
   
  <ul id="list">
    <fieldset>
     
    <li v-for="(task, index) in completeds" :key="index">
      {{ task.title }}
    </li>
  </fieldset>
   </ul>
  
  

 

</template>


<script setup>
import {ref,vModelCheckbox} from 'vue'

// pour stocker la liste des taches 
const tasks=ref([])

//pour stocker les taches en cours d'insertion à la ligne 9 via 'v-model'
const newTasks=ref('')

//Pour stocker les taches completés
const completeds=ref([])

//Ajouter une nouvelle tache à notre liste
const addTask=()=>{
      tasks.value.push({
      title : newTasks.value,
      completed : false,
      VarDate : Date.now()     
    })
   newTasks.value=''
}

//Permet de mettre une tache effectué dans une corbeille
const deleteTasks=()=>{
  
}

//permet d'afficher et masquer à fois chaque que l'on appui sur un boutton 
function displayOrHide(id){
     if(document.getElementById(id).style.display=='none'){
      document.getElementById(id).style.display='block'
     }
     else{
      document.getElementById(id).style.display='none'
     }
}

   // displayOrHide('listCompleted')

//permet d'enlever des taches de la liste des choses à faire lorsqu'elles sont cochés 
//pour les ajoutés à la liste des taches complètés dans 'Display or Hide'
const addcompleteds=(index)=>{
        this.tasks[index].completed
        const completeds= this.tasks.splice(index,1)[0];
        this.completeds.push(completeds)
      
    
  // if(vModelCheckbox){
  //   completeds.value.push({
  //     title : tasks.value,
  //     completed : true,
  //     VarDate : Date.now()     
  //   })
  //   tasks.value=''
    
  //  }
  //  return completeds.value 



  //permet de barrer une tache lorsqu'elle est cochée
// const barTasks=()=>{
//   if(vModelCheckbox){
//     tasks.value.line-through
//     console.log(tasks.value)
//   }
// }  
}



</script>


<style>

</style> -->