<script setup>
import { ref, computed } from 'vue';

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

const newItem = ref("");
const characterCount = computed(()=>{
  return newItem.value.length
});
</script>

<template>
  <span v-bind="attributes">👋🏻</span>
  <h1>
    Hi, my name is 
    <a v-on:click.prevent="blockLeave" :href="'https://github.com/' + username" target="_blank">{{ name }}</a>!
    What is yours ?
  </h1>
  <input v-model="newItem" placeholder="Your name here">
  <p class="counter">
    {{ characterCount }}/200
  </p>
  <a :href>
    <button :disabled>Click to visit my favourite website! If you can...</button>
  </a>
  <h2 v-on:[event]="coding_years++">
    {{
      coding_years > 1 ? `I have been coding for ${coding_years} years.` : "Im a newbie"
    }}
  </h2>
  <h3>Today is {{ getFormattedDate(new Date())}}</h3>
</template>

