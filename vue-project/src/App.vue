<script lang="ts">
// eslint-disable-next-line @typescript-eslint/no-unused-vars
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'App',
  /*components: {
    HelloWorld
  },*/
  data() {
    return {}
  }
})
</script>

<template>
  <header>
    <div class="wrapper">
      <!--HelloWorld /-->

      <nav class="nav--style">
        <div class="div--subnav">
          <RouterLink to="/" class="home">Home</RouterLink>
          <RouterLink to="/articles" class="articles">Articles</RouterLink>
          <RouterLink to="/about" class="about">About</RouterLink>
        </div>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
.nav--style {
  position: fixed;
  top: 0px;
  right: 0px;
  left: 0px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: right;
  font-size: 1.4rem;
  background: linear-gradient(160deg, skyblue, dodgerblue);
  box-shadow: 0px 0px 4px #fff;
}
.div--subnav {
  width: 50%;
  display: flex;
  justify-content: space-around;
}
.home {
  color: cyan;
  text-shadow: 1px 1px 1px #242424;
}
.articles {
  color: cyan;
  text-shadow: 1px 1px 1px #242424;
}
.about {
  color: cyan;
  text-shadow: 1px 1px 1px #242424;
}
</style>
