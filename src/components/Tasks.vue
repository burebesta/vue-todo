<template>
    
    <div>
      <div class='task-container' v-for="task in tasks.slice().reverse()" :key="task.id" 
      :class="[task.reminder ? 'active' : '']">
        <!-- v-for="item in items.slice().reverse()" TO REVERSE ORDER -->
        <IndividualTask @toggle-reminder='$emit("toggle-reminder", task.id)' :individualTask="task" />
        <i @click='deleteTask(task.id)' class="fa-solid fa-xmark"></i>
      </div>
    </div>
  
</template>


<script>
import IndividualTask from './IndividualTask.vue'

export default {
    name: "Tasks",
    props: {
        tasks: Array,
    },
    components: {
      IndividualTask,
    },
    methods: {
      deleteTask(id) {
        this.$emit('delete-task', id);
      }
    },
    // emits: ['delete-task'],
    
}
</script>

<style scoped> 
  
.task-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: rgb(223, 233, 243);
  margin: 20px;
  padding: 10px;
  border: 2px solid rgba(0,0,0, 0.3);
  border-radius: 5px;
}

.active {
  border-left: 10px solid green;
  border-top-left-radius: 0px;
  border-bottom-left-radius: 0px;
}

.fa-solid {
  color: rgb(255, 65, 65);
  font-size: 1.7rem;
}

.fa-solid:hover {
  transform: scale(1.2);
  cursor: pointer;
}
</style>