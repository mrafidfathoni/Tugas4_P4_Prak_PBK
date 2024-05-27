<template>
  <div id="app">
    <ParentComponent>
      <template v-slot>
        <p class="slot-content">This is additional content inside the slot!</p>
      </template>
    </ParentComponent>
  </div>
</template>

<script>
import ParentComponent from "./components/ParentComponent.vue";

export default {
  name: "App",
  components: {
    ParentComponent
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.slot-content {
  padding: 10px;
  border: 1px dashed #333;
  background-color: #fff8e1;
  border-radius: 5px;
}
</style>
