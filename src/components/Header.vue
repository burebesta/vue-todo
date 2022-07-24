<template>
  <div class="header-container">
    <h1>Task Tracker</h1>
    <ButtonComponent @change-button='$emit("change-button")'/>
  </div>

</template>

<script>
import ButtonComponent from './ButtonComponent.vue'

export default {
  name: 'Header',
  components: {
    ButtonComponent,
  },
  data() {
    return {
      
    }
  }
}
</script>

<style>
.header-container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin-bottom: 50px;
}
</style>