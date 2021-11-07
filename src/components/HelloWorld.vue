<template>
  <h1>{{ msg }}</h1>
  <button @click="inCrement"> count is: </button>
  <router-link to="/about" >about</router-link>
  <p>{{ count }}</p>
</template>

<script>
import { defineComponent, computed } from 'vue'
import { useStore } from 'vuex'
import { key } from '../../store'

export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: {
      type: String,
      default: ''
    }
  },
  setup() {
    const store = useStore(key)

    const count = computed(() => store.state.count)

    return {
      msg:'HelloWorld',
      count,
      inCrement: () => store.commit('increment')
    }
  }
})
</script>


<!--<script setup>-->
<!--import { ref } from 'vue'-->

<!--defineProps({-->
<!--  msg: String-->
<!--})-->

<!--const count = ref(0)-->
<!--</script>-->

<!--<template>-->
<!--  <h1>{{ msg }}</h1>-->

<!--  <p>-->
<!--    Recommended IDE setup:-->
<!--    <a href="https://code.visualstudio.com/" target="_blank">VSCode</a>-->
<!--    +-->
<!--    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>-->
<!--  </p>-->

<!--  <p>-->
<!--    <a href="https://vitejs.dev/guide/features.html" target="_blank">-->
<!--      Vite Documentation-->
<!--    </a>-->
<!--    |-->
<!--    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>-->
<!--  </p>-->

<!--  <button type="button" @click="count++">count is: {{ count }}</button>-->
<!--  <p>-->
<!--    Edit-->
<!--    <code>components/HelloWorld.vue</code> to test hot module replacement.-->
<!--  </p>-->
<!--</template>-->

<!--<style scoped>-->
<!--a {-->
<!--  color: #42b983;-->
<!--}-->
<!--</style>-->
