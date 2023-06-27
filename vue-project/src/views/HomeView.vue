<script lang="ts">
import TodoList from '../components/TodoList.vue'
import { defineComponent } from 'vue';
export default defineComponent({
  name:'HomeView',
  components: {
    TodoList
  },
  data() {
    return {
    }
  }
})
</script>

<template>
  <main>
    <TodoList />
  </main>
</template>

<style scoped>

</style>