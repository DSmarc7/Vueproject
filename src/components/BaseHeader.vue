<template>
    <header>
      <nav>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">About</a></li>
          <!-- Add more navigation links as needed -->
        </ul>
      </nav>
      <div class="user-info">
        <p>Efrei Student</p>
      </div>
    </header>
  </template>

<script>
export default {
    name: 'BaseHeader'
}
</script>

<style scoped>
h1 {
    font-size: 3rem;
    margin-bottom: 1rem;
}

p {
    font-size: 1.5rem;
}
</style>
