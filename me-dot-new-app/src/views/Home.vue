<template>
  <v-container>
    <!-- Headline -->
    <v-card>
      <div class="text-h4 text-md-h2 pb-5 pt-5 text-center">
        Ai Cover Letter Generator
      </div>
      <div class="text-subtitle-2 text-md-subtitle-1 text-center pb-5">
        Generate a personalised cover letter in a few minutes!
      </div>

      <!-- Form -->
      <CoverLetterForm></CoverLetterForm>
    </v-card>
  </v-container>
</template>

<script setup>
import { ref } from "vue";
import CoverLetterForm from "@/components/CoverLetterForm.vue";
</script>
