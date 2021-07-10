<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
// @ is an alias to /src


export default {
  name: 'Home',
  setup(){

    const p = ref(null)

    const name = ref('faraz')
    const age = ref(23)

    const handleClick = () => {
      // console.log(p, p.value)
      // p.value.classList.add('test')

      name.value = 'musab'
      age.value = 15
    }

    return {
      name, age, handleClick, p
    }
  }
}
</script>
