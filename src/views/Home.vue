<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">Toggle Posts</button>
    <button @click="posts.pop()">Delete post</button>
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
import { ref, reactive } from '@vue/reactivity'
import { computed, watchEffect } from '@vue/runtime-core'
import {watch} from 'vue'
// @ is an alias to /src


export default {
  name: 'Home',
  components: { PostList },
  setup(){

    const posts =ref([
      { title: 'welcome to the blog', body: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi fugiat quos impedit corporis mollitia neque corrupti sunt nesciunt, voluptates, quia exercitationem omnis explicabo soluta a est harum iste quam obcaecati. Ipsam vitae velit ea natus magni optio autem labore. Sapiente, cupiditate adipisci consequuntur officia sed exercitationem repellendus error aut pariatur voluptas reprehenderit et minus nulla corrupti nam corporis. Dolore, quod.Atque iusto laborum quis accusamus, magnam labore quia saepe ex perferendis. Enim ad quod asperiores aliquid corporis cupiditate adipisci exercitationem itaque commodi voluptas delectus eius consequuntur non molestiae, officia aperiam.Tempora, quis expedita provident voluptatibus animi deleniti ex illum quidem aliquid quas, minima impedit magnam odit officia et accusamus maiores excepturi soluta quo eveniet! Assumenda eveniet numquam beatae quidem ipsa?Consequuntur error necessitatibus laborum suscipit ipsa nam, dolore voluptatem est aliquam assumenda et dolorem, alias eum sunt magni quisquam? Vero, mollitia. Odio veritatis quo eveniet, error eum doloribus. Maxime, beatae.Placeat iste laborum hic non illo atque temporibus facere tempore fugit voluptatibus! Accusantium, in perferendis nam eos, minus facilis inventore placeat explicabo numquam, aut itaque aliquam? Odio laborum eius ex.Nulla qui, error sint in magni ab magnam ea doloremque, autem voluptatum quisquam a saepe sit nobis deleniti voluptatem. Animi harum nam, voluptas ut nesciunt consequuntur reiciendis commodi doloribus iusto?Beatae, doloremque placeat in illo eveniet nisi ipsa quisquam nostrum blanditiis sequi veniam a, reprehenderit optio dolor quaerat porro minima ex maiores voluptatum esse impedit molestias consequatur nulla. Aut, laborum!Modi quisquam repudiandae corrupti harum vel? Nostrum modi quae est dicta sit labore sapiente tempora commodi harum quaerat odit pariatur enim, alias hic quibusdam mollitia totam amet rerum cumque accusantium?Eligendi culpa quaerat at eum temporibus itaque odit veniam repudiandae unde? Vero atque eaque assumenda minima! Quas sed commodi delectus consectetur quis, necessitatibus, numquam aliquam, consequuntur amet quia vel iste?', id: 1 },
      { title: 'top 5 HTML CSS tips', body: 'lorem ipsum', id: 2 }

    ])

    const showPosts = ref(true)

    return { posts, showPosts }

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
