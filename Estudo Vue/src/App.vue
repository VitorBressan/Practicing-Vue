<script setup>
import { ref, computed } from 'vue';

const attributes = {
  id: 'big_emoji',
  class: 'waving',
};

const name = ref('Bressan');
const href = ref('https://orteil.dashnet.org/cookieclicker/');
const coding_years = ref(3);
const getFormattedDate = (date) => {
  const options = { year: 'numeric', month: 'long', day: 'numeric' };
  return date.toLocaleDateString('en-UK', options);
};

const githubUsername = ref('VitorBressan');
const event = ref('dblclick');
const disabled = ref(true);
const blockLeaveGithub = () => {
  alert("Follow me on github!");
};

const userTypedName = ref("");
const characterCount = computed(()=>{
  return userTypedName.value.length
});
</script>

<template>
  <span v-bind="attributes">👋🏻</span>


  <h1>
    Hi, my name is 
    <a v-on:click="blockLeaveGithub" :href="'https://github.com/' + githubUsername" target="_blank">{{ name }}</a>!
    What is yours ?
  </h1>
  <input v-model="userTypedName" placeholder="Your name here">
  <p class="counter">
    {{ characterCount }}/200
  </p>


  <a :href target="_blank">
    <button :disabled>Click to visit my favorite website! If you can...</button>
  </a>
  <button v-on:click="disabled = !disabled">Toggle</button>
  <p>{{ disabled ? "Disabled" : "Enabled" }}</p>
  

  <h2 v-on:[event]="coding_years++">
    {{
      coding_years > 1 ? `I have been coding for ${coding_years} years.` : "Im a newbie"
    }}
  </h2>
  <h3>Today is {{ getFormattedDate(new Date())}}</h3>
</template>

