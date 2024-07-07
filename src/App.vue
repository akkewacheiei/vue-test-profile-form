<script setup>
import { reactive } from "vue";

const gendersList = ["ชาย", "หญิง", "ไม่ระบุ"];
const interestsList = ["หนังสือ", "กีฬา", "การเมือง", "เกม", "เขียนเว็บ"];

const formData = reactive({ interests: [] });

const submitForm = () => {
  console.log("submitForm !!");
  console.log("formData :", formData);
  console.log("interests :", formData.interests.join());
};
</script>

<template>
  <div>
    <div>
      <div>Firstname</div>
      <input type="text" name="firstname" v-model="formData.firstname" />
    </div>
    <div>
      <div>Lastname</div>
      <input type="text" name="lastname" v-model="formData.lastname" />
    </div>
    <div>
      <div>Gender</div>
      <div v-for="gender in gendersList">
        <input
          type="radio"
          name="gender"
          :value="gender"
          v-model="formData.gender"
        />
        {{ gender }}
      </div>
    </div>
    <div>
      <div>Interests</div>
      <div v-for="interest in interestsList">
        <input
          type="checkbox"
          name="interest"
          :value="interest"
          v-model="formData.interests"
        />
        {{ interest }}
      </div>
    </div>
    <div>
      <div>Description</div>
      <textarea v-model="formData.description"></textarea>
    </div>
    <button @click="submitForm()">ส่ง Form</button>
  </div>
</template>
