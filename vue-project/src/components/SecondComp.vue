<template>
    <h2>SecondComp</h2>
    <div v-for="post in getPosts" :key="post?.id">
        <div v-if="post">
            <h2>{{ post.id }}</h2>
            <h2>{{ post.title }}</h2>
            <h3>{{ post.body }}</h3>
        </div>
        <div v-else="error">
            <h2>{{ error?.message }}</h2>
        </div>
    </div>
</template>

<script lang="ts">
import axios from "axios";
import { defineComponent } from 'vue';
type DataProps = {
    id: number,
    title: string,
    body: string
}
export default defineComponent({
    name:'SecondComp',
    data() {
        return {
            getPosts,
            posts: []
        }
    },
    methods: {
        getPosts() {
            axios.get('http://...')
                .then((response: { data: DataProps; }) => {
                    response.data
                })
                .catch((error: { message: string; }) => {
                    console.log(error.message)
                })
        }
    }
})
</script>

<style scoped>

</style>
