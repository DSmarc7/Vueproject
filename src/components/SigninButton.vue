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
  import { signInAndGetUser } from '@/lib/microsoftGraph.js'; // Import the signInAndGetUser function
  
  export default {
    name: 'SigninButton',
   
    data() {
      return {
        isSigningIn: false,
        user: null,
      };
    },
    methods: {
      async handleSignIn() {
        this.isSigningIn = true;
        try {
          this.user = await signInAndGetUser();
        } finally {
          this.isSigningIn = false;
        }
      },
    },
  };
</script>
  