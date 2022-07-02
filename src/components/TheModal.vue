<template>
  <div v-if="show" class="modal">
    <input v-model="localJobTitle.name"/><br>
    <input v-model="localJobTitle.surname"/><br>
    <button @click="closeModal">Close component</button>
  </div>
</template>
<script setup>
import {defineProps, defineEmits, toRef} from 'vue'
const props = defineProps({
  show: {
    type: Boolean,
    default: false
  },
  jobTitle: {
    type: Object,
    default: () => {
      return {
        name: null,
        surname: null
      }
    }
  }
})
const emit=defineEmits(['closeModal'])
const closeModal=()=>{
  emit('closeModal')
}
const localJobTitle = toRef(props,'jobTitle');
</script>
<style scoped>
.modal{
  position:fixed;
  border:2px solid black;
  top:50%;
  left:50%;
  padding:15px;
}
button{
  margin-top:15px;
}
</style>
