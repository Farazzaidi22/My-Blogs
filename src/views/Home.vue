<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else>
      <Spinner />
    </div>

    <!-- <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">Toggle Posts</button>
    <button @click="posts.pop()">Delete post</button> -->

    <!-- <input type="text" v-model="search">
    <p>search term - {{ search }}</p>
    <button @click="handleClick">Stop watch</button>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div> -->

    <!-- <h2>Refs</h2>
    <p>{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">Update ninja one</button>

    <h2>Reactive</h2>
    <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">Update ninja two</button> -->
  </div>
</template>

<script>
import PostList from '../components/PostList.vue'
import getPosts from '../composables/getPosts'
import Spinner from '../components/Spinner.vue'

// import { ref, reactive } from '@vue/reactivity'
// import { computed, watchEffect } from '@vue/runtime-core'
// import {watch} from 'vue'
// @ is an alias to /src


export default {
  name: 'Home',
  components: { PostList, Spinner },
  setup(){

    const { posts, error, load} = getPosts()

    load()

    return { posts, error }


    // const showPosts = ref(true)

    // const search = ref('')
    // const names = ref(['faraz', 'mujtaba', 'rafay', 'muaz', 'rasheed', 'amil', 'haseeb', 'raza'])

    // const stopWatch = watch(search, () => {
    //   console.log('watch has ran')
    // })

    // const stopEffect = watchEffect(() => {
    //   console.log('watchEffect has ran', search.value)
    // })

    // const matchingNames = computed(() => {
    //   return names.value.filter((name) => name.includes(search.value))
    // })

    // const handleClick = () => {
    //   stopWatch()
    //   stopEffect()
    // }

    // return {names, search, matchingNames, handleClick}

    // const ninjaOne = ref({name: 'faraz', age: 23})
    // const ninjaTwo = reactive({name: 'Kounpal', age: 23})

    // const updateNinjaOne = () => {
    //   ninjaOne.value.age = 22
    // }

    // const updateNinjaTwo = () => {
    //   ninjaTwo.age = 21
    // }
    
    // return{
    //   ninjaOne, ninjaTwo, updateNinjaOne, updateNinjaTwo
    // }
  }
}
</script>

<style scoped>
  .home {
    max-width: 1200px;
    margin: 0 auto;
    padding: 10px;
  }
</style>
