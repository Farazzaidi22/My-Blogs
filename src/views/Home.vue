<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p>{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">Update ninja one</button>

    <h2>Reactive</h2>
    <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">Update ninja two</button>
  </div>
</template>

<script>
import { ref, reactive } from '@vue/reactivity'
// @ is an alias to /src


export default {
  name: 'Home',
  setup(){

    const ninjaOne = ref({name: 'faraz', age: 23})
    const ninjaTwo = reactive({name: 'Kounpal', age: 23})

    const updateNinjaOne = () => {
      ninjaOne.value.age = 22
    }

    const updateNinjaTwo = () => {
      ninjaTwo.age = 21
    }
    
    return{
      ninjaOne, ninjaTwo, updateNinjaOne, updateNinjaTwo
    }
  }
}
</script>
