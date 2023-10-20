<template>
    <div class="homepage">
      <h1>Welcome to My Awesome Website!</h1>
      <p>Explore the incredible content we have to offer.</p>
      <base-button @click="exploreWebsite" margin="10px" color="primary">Primary Button</base-button>
      <base-button @click="exploreWebsite" margin="10px" color="warn">Warning Button</base-button>
      <base-button @click="exploreWebsite" margin="10px" color="danger">Danger Button</base-button>
      <base-button :disabled="true" margin="10px" color="primary">Disabled Primary Button</base-button>
      <async-button @click="exploreWebsite" margin="10px" color="danger">Danger Button</async-button>
    <base-button :disabled="true" margin="10px" color="primary">Disabled Primary Button</base-button>
    </div>
  </template>
  
  <script>
  import BaseButton from './BaseButton.vue';
  import AsyncButton from './AsyncButton.vue';

  
  export default {
    name: 'HomePage',
    components: {
      'base-button': BaseButton,
      'async-button': AsyncButton,
    },
    methods: {
      exploreWebsite() {
        // Handle the button click event
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
  