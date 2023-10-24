<template>
  <header>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <!-- Add more navigation links as needed -->
        <li><SigninButton @click="signInUser" margin="10px" color="primary">Sign In</SigninButton></li>
      </ul>
    </nav>
    <div class="user-info">
      <p>Efrei Student</p>
    </div>
  </header>
</template>

<script>
import SigninButton from './SigninButton.vue'; // Import your SigninButton component here

export default {
  name: 'BaseHeader',
  components: {
    SigninButton, // Register SigninButton as a component
  },
  methods: {
    signInUser() {
      // Handle the sign-in logic here
    },
  },
};
</script>




<style scoped>
h1 {
    font-size: 3rem;
    margin-bottom: 1rem;
}

p {
    font-size: 1.5rem;
}
nav{
    background-color:  royalblue; 
    color: #fff; 
    padding: 10px;
    text-align: center;
}
nav ul{

    display: flex;
    justify-content: center;
    list-style: none;
    margin: 0;
    padding: 0;
}
nav ul li{
    margin: 0 10px;
}
nav ul li a{
    text-decoration: none;
    color: inherit;
}
</style>
