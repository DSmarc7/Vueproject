<template>
    <div>
      <base-header />
      <slot></slot>
      <base-footer />
    </div>
</template>
  
  <script>
  import BaseHeader from './BaseHeader.vue'; // Import the BaseHeader component
  import BaseFooter from './BaseFooter.vue'; // Import the BaseFooter component
  
  export default {
    components: {
      'base-header': BaseHeader,
      'base-footer': BaseFooter,
    },
  };
  </script>
  
  <style scoped>
  /* Add scoped CSS styles for the BaseLayout component if needed */
  </style>
  