<script setup>
import Footer from './components/Footer.vue';
import Header from "./components/Header.vue"
import { ref, computed } from 'vue';

const attributes = {
  id: 'big_emoji',
  class: 'waving',
};

const name = ref('Bressan');
const href = ref('https://orteil.dashnet.org/cookieclicker/');
const coding_years = ref(3);

const githubUsername = ref('VitorBressan');
const event = ref('dblclick');
const disabled = ref(true);
const blockLeaveGithub = () => {
  alert("Follow me on github!");
};

const userTypedSkill = ref("");
const characterCount = computed(()=>{
  return userTypedSkill.value.length
});

const skillSet = ref([
  "Python",
  "VBA",
  "SqlAlchemy",
  "Flask",
  "Git/GitHub",
  "Excel"
])
</script>


<template>
  <!--
CHALLENGE: Create and use a Header.vue
           component using the provided HTML and CSS
STEP 1: Create a Header.vue file in /components
STEP 2: Structure the file with <script setup>,
        <template>, and <style scoped>
STEP 3: Cut the entire <header> element and it's contents
        and put in the template section of Header.vue
STEP 4: Cut all the Header related styles and
        put in the styles section of Header.vue
STEP 5: Import the Header component into App.vue
STEP 6: Use the Header component in place of <header>
-->
<Header/>

<span v-bind="attributes">👋🏻</span>
  <h1>
    Hi, my name is 
    <a v-on:click="blockLeaveGithub" :href="'https://github.com/' + githubUsername" target="_blank">{{ name }}</a>!
  </h1>
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
  <h3> Skill Set: </h3>
  <input v-model="userTypedSkill" v-on:keyup.enter="skillSet.push(userTypedSkill)" placeholder="Type a skill here"> 
  <button v-on:click="skillSet.push(userTypedSkill)">
    Register
  </button>
  <p class="counter">
    {{ characterCount }}/200
  </p>
  
  <ul class="skill-list">
    <li v-for="skill in skillSet"> {{ skill }}</li>
  </ul>
    

<Footer/>
</template>

<style>
  .skill-list{
    list-style-type: none;
    padding: 0;
    margin: 0
  }
</style>