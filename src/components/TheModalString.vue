<template>
  <div v-if="show" class="modal">
    <input v-model="localJobTitle"/><br>
    <button @click="closeModal">Close component</button>
  </div>
</template>
<script setup>
import {defineProps, defineEmits, computed} from 'vue'
const props=defineProps({
  show:{
    type:Boolean,
    default:false
  },
  jobTitle:{
    type: String,
    default:'defaultValue'
  }
})
const emit=defineEmits(['closeModal'])
const closeModal=()=>{
  emit('closeModal')
}
const localJobTitle=computed({
  get(){
    return props.jobTitle
  },
  set(newValue){
    emit('changeValue',newValue)
  }
})
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
