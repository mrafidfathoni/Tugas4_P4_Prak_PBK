<template>
    <div class="child-container">
      <input v-model="message" placeholder="Type your message here" />
      <button class="send-button" @click="sendMessage">
        <i class="fas fa-paper-plane"></i> Send Message
      </button>
    </div>
  </template>
  
  <script>
  export default {
    name: "ChildComponent",
    data() {
      return {
        message: ""
      };
    },
    methods: {
      sendMessage() {
        if (this.message.trim() !== "") {
          this.$emit("messageSent", this.message);
          this.message = ""; // Clear input after sending message
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .child-container {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    margin: 20px 0;
  }
  .send-button {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px 20px;
    font-size: 16px;
    color: #fff;
    background-color: #007bff;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.2s;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  .send-button:hover {
    background-color: #0056b3;
    transform: translateY(-2px);
  }
  .send-button i {
    margin-right: 8px;
  }
  input {
    padding: 10px;
    width: 300px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  </style>
  