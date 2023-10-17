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
