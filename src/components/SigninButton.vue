<template>
  <div>
    <button @click="handleSignIn" :disabled="isSigningIn" color="primary">
      {{ isSigningIn ? 'Signing In...' : 'Sign In' }}
    </button>
    <div v-if="user">
      <p>Logged in as {{ user.name }}</p>
      <p>Email: {{ user.email }}</p>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
import { useStore } from 'vuex';
import { signInAndGetUser } from '@/lib/api.js'; // Import the signInAndGetUser function from your api.js file

export default {
  name: 'SigninButton',

  setup() {
    const store = useStore();
    const isSigningIn = ref(false);

    const handleSignIn = async () => {
      isSigningIn.value = true;
      try {
        // Simulate sign-in logic, e.g., calling an API
        const user = await signInAndGetUser();
        store.commit('setUser', user); // Commit the setUser mutation in the store
      } finally {
        isSigningIn.value = false;
      }
    };

    return { isSigningIn, handleSignIn };
  },
};
</script>
