<script setup>
import { ref, reactive, watchEffect } from "vue";


const formData = reactive({
  firstname: "",
  lastname: "",
});
const fullname = ref("");

watchEffect(
() => {
console.log('formData from watchEffect', formData);
fullname.value = `${formData.firstname} ${formData.lastname}`
}
);
</script>

<template>
  <div>
    <div>Fullname {{ fullname }}</div>
    <input type="text" v-model="formData.firstname" />
    <input type="text" v-model="formData.lastname" />
  </div>
</template>
