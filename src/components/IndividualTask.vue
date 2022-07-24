<template>
  
  <div class="individual-task" @click="toggleReminder(individualTask.id)">
    <div class='task-text'>
      {{individualTask.text}}
    </div>
      {{individualTask.day}}
  </div>
  
</template>

<script>
export default {
    name: "IndividualTask",
    props: {
        individualTask: Object,
    },
    methods: {
      toggleReminder(id) {
        this.$emit('toggle-reminder', id)
      },
      deleteTask(id) {
      }
    }
    
}
</script>

<style>

.individual-task {
  padding-left: 20px;
  width: 100%;
}

.task-text {
  font-size: 1.2rem;
  font-weight: 500;
}
</style>