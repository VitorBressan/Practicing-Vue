<script setup>
  const getFormattedDate = (date) => {
  const options = { year: 'numeric', month: 'long', day: 'numeric' };
  return date.toLocaleDateString('en-UK', options);
};
</script>

<template>
<footer>
  <p>Today is {{ getFormattedDate(new Date())}}</p>
</footer>
</template>

<style scoped>
/* FOOTER STYLES */
footer {
  width:100%;
  background:#D17862;
  color:white;
  text-align:center;
  padding:10px;
  margin-top:auto;
}
/* ----------------- */
</style>