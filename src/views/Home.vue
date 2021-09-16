<template>
  <h2>Home</h2>
  <p ref='para'>My name is {{ name }} and my age is {{ age }}</p>
  <!-- <p ref='para_another'>2nd Paragraph</p> -->
  <button @click="handleClick">Click me</button>
</template>

<script>
import {ref} from 'vue'
  export default {
    name: 'Home',
    setup() {
      console.log("setup called")
      const para = ref(null)
      // const para_another = ref(null)


      let name = "Sanju"
      let age = 40


      const handleClick = () => {
        console.log(para)
        console.log("_rawValue: "+para._rawValue)
        console.log("innerText: "+para.value.innerText)
        para.value.classList.add("test")
      }

      return { name, age, handleClick, para }
      // return {name, age, handleClick, para}
    }
  }
</script>
