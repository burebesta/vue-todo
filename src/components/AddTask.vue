<template>
<form @submit.prevent="emitSubmitted">
  <div class="form-item">
    <div class="label-div"><label for="task-name">Task Name</label></div>
    <input type="text" id="task-name" name="task-name" v-model="this.name" placeholder="Enter task name here">
  </div>
  <div class="form-item">
    <div class="label-div"><label for="task-date">Task Date</label></div>
    <input type="text" id="task-name" name="task-date" v-model="this.date" placeholder="Enter date here">
  </div>
  <div class="form-item">
    <div class="label-div"><label for="task-reminder">Reminder</label></div>
    <input type="checkbox" id="task-reminder" name="task-reminder" v-model="this.reminder">
  </div>    
    <button class="button-form" type="submit">Add task</button>
</form>
</template>

<script>
export default {
  name: 'AddTask',
  data() {
    return {
      name: '',
      date: '',
      reminder: false,
    }
  },
  methods: {
    emitSubmitted(){
      if (this.name && this.date) {
      this.$emit('submitted',[this.name,this.date,this.reminder])
      this.name = ''
      this.date = ''
      this.reminder = ''
      }      
  }
}
}

</script>

<style>

input[type='text'] {
  width: 250px;
  padding-left: 10px;
}
.form-item {
  background-color: ed;
  margin: 20px;
  display: flex;
  align-items: center;
  gap: 20px;
}
.label-div {
  width: 100px;
}

.button-form {
  margin-left: 20px;
  padding: 10px 20px;
}

.button-form:hover {
  cursor: pointer;
}


input {
  height: 30px;
}
input[type="checkbox"] {
  width: 30px;
}

</style>