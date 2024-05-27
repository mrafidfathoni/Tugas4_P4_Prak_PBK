<template>
    <div class="nested-container">
      <h2 class="subtitle">Nested Component</h2>
      <ChildComponent @messageSent="forwardMessage"></ChildComponent>
    </div>
  </template>
  
  <script>
  import ChildComponent from "./ChildComponent.vue";
  
  export default {
    name: "NestedComponent",
    components: {
      ChildComponent
    },
    methods: {
      forwardMessage(message) {
        this.$emit("messageForwarded", message);
      }
    }
  };
  </script>
  
  <style scoped>
  .nested-container {
    padding: 20px;
    border: 1px solid #bbb;
    border-radius: 10px;
    background-color: #e6f7ff;
    margin-top: 15px;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
  }
  .subtitle {
    text-align: center;
    color: #555;
    margin-bottom: 15px;
    font-size: 1.5em;
  }
  </style>
  