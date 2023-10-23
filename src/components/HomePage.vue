<template>
  <div class="homepage">
    <h1>Welcome to My Awesome Website!</h1>
    <p>Explore the incredible content we have to offer.</p>
    <base-button @click="exploreWebsite" margin="10px" color="primary">Primary Button</base-button>
    <base-button @click="exploreWebsite" margin="10px" color="warn">Warning Button</base-button>
    <base-button @click="exploreWebsite" margin="10px" color="danger">Danger Button</base-button>
    <base-button :disabled="buttonDisabled" margin="10px" color="primary">Dynamic Waiting Button</base-button>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
  name: 'HomePage',
  components: {
    'base-button': BaseButton,
  },
  data() {
    return {
      buttonDisabled: false,
      clickCount: 0,
    };
  },
  methods: {
    exploreWebsite() {
      this.clickCount++;
      this.disableButtonForDynamicTime(this.clickCount).then(() => {
        this.buttonDisabled = false;
      });
    },
    disableButtonForDynamicTime(waitTime) {
      this.buttonDisabled = true;
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve();
        }, waitTime * 1000); // Increase wait time by 1 second per click
      });
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
  color: #0074d9;
}

p {
  font-size: 1.2rem;
  color: #333;
}
</style>
