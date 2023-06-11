<script lang="ts">
// eslint-disable-next-line @typescript-eslint/no-unused-vars
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {}
  }
})
</script>

<template>
  <header>
    <div class="wrapper">
      <HelloWorld />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

</style>
