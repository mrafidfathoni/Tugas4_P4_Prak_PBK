<template>
    <div class="parent-container">
      <h1 class="title">Parent Component</h1>
      <NestedComponent @messageForwarded="displayMessage"></NestedComponent>
      <transition-group name="message" tag="div" class="messages-container">
        <div v-for="(msg, index) in messages" :key="index" class="message-card">
          <div class="avatar">
            <i class="fas fa-user"></i>
          </div>
          <div class="message-content">
            <p>{{ msg }}</p>
          </div>
        </div>
      </transition-group>
      <div class="slot-container">
        <slot></slot> <!-- Slot untuk menampilkan komponen lain -->
      </div>
    </div>
  </template>
  
  <script>
  import NestedComponent from "./NestedComponent.vue";
  
  export default {
    name: "ParentComponent",
    components: {
      NestedComponent
    },
    data() {
      return {
        messages: []
      };
    },
    methods: {
      displayMessage(message) {
        this.messages.push(message);
      }
    }
  };
  </script>
  
  <style scoped>
  .parent-container {
    padding: 30px;
    border: 2px solid #ccc;
    border-radius: 15px;
    max-width: 700px;
    margin: 20px auto;
    background-color: #f0f8ff;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  .title {
    text-align: center;
    color: #333;
    font-size: 2em;
    margin-bottom: 20px;
  }
  .messages-container {
    margin-top: 20px;
    padding: 15px;
    border-radius: 10px;
    text-align: left;
  }
  .message-card {
    display: flex;
    align-items: center;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ddd;
    border-radius: 10px;
    background-color: #fff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
  }
  .message-card:hover {
    transform: translateY(-2px);
  }
  .avatar {
    margin-right: 10px;
    font-size: 1.5em;
    color: #007bff;
  }
  .message-content {
    flex-grow: 1;
  }
  .slot-container {
    margin-top: 20px;
  }
  .message-enter-active, .message-leave-active {
    transition: all 0.5s;
  }
  .message-enter, .message-leave-to {
    transform: translateY(20px);
    opacity: 0;
  }
  </style>
  