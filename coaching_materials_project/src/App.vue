<template>
  <h1 v-bind:title="message" v-bind:class="{ red: isRed }">{{ title }}</h1>
  <h2>Data of {{ fullName }}</h2>
  <p>Name: {{ fullName }}</p>

</template>

<script>
import { computed } from 'vue';

  export default {
    data() {
      return {
        title: "Info About Me",
        message: "I like you.",
        isRed: true,
        user: {
          firstName: "Shuzo",
          lastName: "Shinagawa"
        },
      }
    },
    
    computed: {
      fullName() {
        return this.user.firstName + " " + this.user.lastName
      },
    },
  }
</script>

<style>
  .red {
    color: red;
  }
</style>