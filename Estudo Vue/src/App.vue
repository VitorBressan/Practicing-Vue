<script setup>
import { ref } from 'vue';

//data
const name = ref('Bressan');
const href = ref('https://www.scrimba.com');
const disabled = ref(true);
const attributes = {
  id: 'big_emoji',
  class: 'waving',
};
const coding_years = ref(3);
const getFormattedDate = (date) => {
  const options = { year: 'numeric', month: 'long', day: 'numeric' };
  return date.toLocaleDateString('en-UK', options);
};
const username = ref('VitorBressan');
const event = ref('dblclick');
const blockLeave = () => {
  alert("You can't leave!");
};
</script>

<template>
  <span v-bind="attributes">👋🏻</span>
  <h1>
    Hi, my name is <a v-bind:href="'https://github.com/' + username" target="_blank">{{ name }}</a>
  </h1>
  <a :href>
    <button :disabled>Click to visit my favourite website! If you can...</button>
  </a>
  <h2>
    {{
      coding_years > 1 ? `I have been coding for ${coding_years} years.` : "Im a newbie"
    }}
  </h2>
  <h3>Today is {{ getFormattedDate(new Date())}}</h3>
</template>

