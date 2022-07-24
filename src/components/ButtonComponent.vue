<template>
  <button :class="[show ? 'active' : 'inactive']" @click="showTaskForm">{{show ? 'Close' : 'Add task'}}</button>
</template>

<script>
export default {
  name: 'ButtonComponent',
  props: {
    color: String
  },
  data(){
    return {
      show : false
    }
  },
  methods: {
    showTaskForm() {
      this.show = !this.show;
      this.$emit('change-button', this.show)
    }
  }
}
</script>

<style scoped>

.active {
  background-color: rgb(255, 144, 144);
}

.inactive {
  background-color: rgb(140, 255, 140);
}

button {
  font-size: 1.5rem;
  padding: 5px 10px;
  border-radius: 5px;
}

button:hover {
  cursor: pointer;
}

</style>