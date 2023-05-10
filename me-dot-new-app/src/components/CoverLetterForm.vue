<template>
  <v-container>
    <v-form @submit.prevent="submit">
      <v-row>
        <v-col cols="12" sm="6">
          <v-text-field
            v-model="fullName"
            :rules="textRules"
            required
            counter="30"
            name="Your Name"
            label="Your Name"
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6">
          <v-text-field
            v-model="companyName"
            :rules="textRules"
            required
            counter="30"
            name="Company Name"
            label="Name of company you're applying to"
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" sm="6">
          <v-text-field
            v-model="position"
            :rules="textRules"
            required
            counter="30"
            name="Position"
            label="Position you're applying for"
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6">
          <v-text-field
            v-model="experience"
            :rules="textRules"
            required
            counter="30"
            name="Most relevant experience"
            label="Most relevant experience / project"
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row class="pb-3">
        <v-btn block type="submit" color="success">Generate</v-btn>
      </v-row>
    </v-form>
  </v-container>
</template>

<script setup>
import { ref } from "vue";
import { watch } from "vue";

const watcher = watch({});
//form data
const fullName = ref("");
const companyName = ref("");
const position = ref("");
const experience = ref("");

//input validation
const isValid = ref(false);
const textRules = ref([
  (value) => {
    if (!value) {
      return "Input Required";
    }
    isValid.value = true;
    return true;
  },
]);

// !!submit!!
function submit() {
  //only submit if the data is valid
  if (isValid.value) {
    //creating the object to send to our worker
    const formDataToSubmit = {
      fullName: fullName.value,
      companyName: companyName.value,
      position: position.value,
      experience: experience.value,
    };
    //SEND IT
    console.log(formDataToSubmit);
  }
}
</script>
