<script setup>
  defineProps(["name", "clientName"])
  const getFormattedDate = (date) => {
    const options = { year: 'numeric', month: 'long', day: 'numeric' };
    return date.toLocaleDateString('en-UK', options);
  };

</script>

<template>
<footer>
  <p>{{clientName}} today is {{getFormattedDate(new Date())}}</p>
  <p>Website made by {{name}}</p>
</footer>
</template>

<style scoped>
/* FOOTER STYLES */
footer {
  width:100%;
  background:#D17862;
  color:white;
  text-align:center;
  margin-top:auto;
}
/* ----------------- */
</style>