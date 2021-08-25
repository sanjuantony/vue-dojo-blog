<template>
  <h2>Home</h2>
  <p>My name is {{ name }} and my age is {{ age }}</p>
  <button @click="handleClick">Click me</button>
</template>

<script>
  export default {
    name: 'Home',
    setup() {
      console.log("setup called")

      let name = "Sanju"
      let age = 40

      const handleClick = () => {
        console.log("You clicked me")
      }

      return {name, age, handleClick}
    }
  }
</script>
