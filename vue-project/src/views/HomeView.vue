<script lang="ts">
import SecondComp from '../components/SecondComp.vue'
import { defineComponent } from 'vue';
export default defineComponent({
  name:'HomeView',
  components: {
    SecondComp
  },
  data() {
    return {
    }
  }
})
</script>

<template>
  <main>
    <SecondComp />
  </main>
</template>

<style scoped>

</style>