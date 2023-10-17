<template>
    <div class="homepage">
      <h1>Welcome to My Awesome Website!</h1>
      <p>Explore the incredible content we have to offer.</p>
      <base-button @click="exploreWebsite" margin="10px">BaseButton with Custom Margin</base-button>
      <base-button :disabled="true">Disabled Button</base-button>
    </div>
  </template>
  
  <script>
  import BaseButton from './BaseButton.vue';
  
  export default {
    name: 'HomePage',
    components: {
      'base-button': BaseButton,
    },
    methods: {
      exploreWebsite() {
        // Handle the "BaseButton with Custom Margin" button click event
        // You can add a router push here to navigate to another page.
      },
    },
  };
  </script>
  
  <style scoped>
  .homepage {
    text-align: center;
    padding: 20px;
  }
  
  h1 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: #0074d9; /* Adjust the color as needed */
  }
  
  p {
    font-size: 1.2rem;
    color: #333; /* Adjust the color as needed */
  }
</style>
  