<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <button @click="addModal">Add Modal</button>
  <button @click="editModal">Edit Modal</button>
  {{selectedJobTitle}}
  <TheModal :show="show" :job-title="selectedJobTitle" @close-modal="closeModal" @change-value="changeValue" />
</template>

<script setup>
import {ref} from 'vue'
import TheModal from "./components/TheModal.vue";
const show = ref(false)
const selectedJobTitle = ref(null)
const editModal = () => {
  show.value = true;
  selectedJobTitle.value = null;
}
const addModal = () => {
  show.value = true;
  selectedJobTitle.value = 'kokos'
}
const closeModal = ()=>{
  show.value=false
}
const changeValue=(value)=>{
  selectedJobTitle.value=value;
}
</script>
