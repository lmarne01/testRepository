<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <button @click="addModal">Add Modal</button>
  <button @click="editModal">Edit Modal</button>
  This is Parent variable:{{selectedJobTitle}}
  <TheModal :show="show" :job-title="selectedJobTitle" @close-modal="closeModal" @change-value="changeValue" />
</template>

<script setup>
import {ref,reactive} from 'vue'
import TheModal from "./components/TheModal.vue";
const show = ref(false)
const selectedJobTitle = reactive({name:null,surname:null})
const editModal = () => {
  show.value = true;
  selectedJobTitle.name = null;
  selectedJobTitle.surname = null;
}
const addModal = () => {
  show.value = true;
  selectedJobTitle.name = 'kokos';
  selectedJobTitle.surname = 'kokou';
}
const closeModal = ()=>{
  show.value=false
}
const changeValue=(value)=>{
  selectedJobTitle.value=value;
}
</script>
