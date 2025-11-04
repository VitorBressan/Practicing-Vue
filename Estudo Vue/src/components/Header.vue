<script setup>
const clientName = defineModel("clientName");
</script>

<template>
  <header class="header">
    <p>Whats your name?</p>
    <input v-model="clientName" placeholder="Type your name here"/>
  </header>
</template>

<style scoped>
.header {
  width: 100%;
  background-color: #f5deb3; /* bege claro */
  padding: 5px;
  text-align: center;
  font-size: 1.5rem;
  font-weight: 600;
  color: #333;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
</style>