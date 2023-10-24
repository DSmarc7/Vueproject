<template>
  <div class="homepage">
    <h1>Welcome to My Awesome Website!</h1>
    <p>Explore the incredible content we have to offer.</p>
    <async-button ref="asyncButton" @click="exploreWebsite" margin="10px" color="primary">Click Me</async-button>
    <div v-if="user">
      <p>Logged in as {{ user.name }}</p>
      <p>Email: {{ user.email }}</p>
    </div>
  </div>
</template>

<script>
import AsyncButton from './AsyncButton.vue';
import { computed } from 'vue';
import { useStore } from 'vuex';

export default {
  name: 'HomePage',

  components: {
    'async-button': AsyncButton,
  },

  setup() {
    const store = useStore();
    const user = computed(() => store.state.user);

    const exploreWebsite = () => {
      // Simulate an asynchronous task, e.g., an API call
      this.$refs.asyncButton.startLoading(); // Start loading animation
      setTimeout(() => {
        this.$refs.asyncButton.stopLoading(); // Stop loading animation after 2 seconds
      }, 2000);
    };

    return { user, exploreWebsite };
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
