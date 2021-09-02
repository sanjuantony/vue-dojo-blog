<template>
  <h2>Home</h2>
  <p ref='para'>My name is {{ name }} and my age is {{ age }}</p>
  <!-- <p ref='para_another'>2nd Paragraph</p> -->
  <button @click="handleClick">Click me</button>
  <input type="text" v-model="name">

  <h1>Using Computed Properties of Composition API</h1>
  <p>Search Name: <input type="text" v-model="searchTerm"> </p>
  <div v-for="name in matchingName" :key="name"> {{ name }} </div>
</template>

<script>
import {computed, ref, watch, watchEffect} from 'vue'
  export default {
    name: 'Home',
    setup() {
      console.log("setup called")
      const para = ref(null)
      // const para_another = ref(null)


      const name = ref("Sanju")
      const age = ref(40)

      const handleClick = () => {
        // console.log(para)
        // console.log("_rawValue: "+para._rawValue)
        // console.log("innerText: "+para.value.innerText)
        // para.value.classList.add("test")
        name.value = "luigi"
        // console.log(para_another, para_another.value)
      }

      const searchTerm = ref('')
      const names = ref(['Sanju', 'Shincy', 'Johann', 'Julia', 'Bobby', 'Dimple', 'Isabelle','Irene', 'David'])

      watch(searchTerm, () => {
          //console.log(searchTerm.value)
        }
      )

      watchEffect(()=>{
        console.log("watchEffect() Triggered", searchTerm.value)
      })

      const matchingName = computed(() => {
        return names.value.filter((name) => name.includes(searchTerm.value))
      })

      return {name, age, handleClick, para, searchTerm, names, matchingName}
    }
  }
</script>
