<template>
    <div class="child-component">
      <h2>Welcome to the Child Component</h2>
      <button @click="emitCustomMessage">Emit Custom Message</button>
    </div>
  </template>
  
  <script>
  import { defineEmits } from 'vue';
  
  export default {
    emits: ['messageEmitted'],
    setup(props, { emit }) {
      const emitCustomMessage = () => {
        const customMessage = 'Hello this message from Child Component!';
        emit('messageEmitted', customMessage);
      };
  
      return {
        emitCustomMessage,
      };
    },
  };
  </script>

<style scoped>
    .child-component {
  background-color: #ffffff;
  padding: 20px;
  margin-top: 20px;
}

.child-component h2 {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

.child-component p {
  margin-bottom: 10px;
}

.child-component button {
  background-color: #3490dc;
  color: #ffffff;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
  