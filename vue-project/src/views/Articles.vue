<template>
    <div>
        <h2>Articles Component</h2>
        <button @click="getPosts">Loader</button>
        <div v-if="errorMsg">
            <h2>{{ errorMsg }}</h2>
        </div>
        <div v-for="post in posts.slice(0, 20)" :key="post.id">
            <h2>{{ post.id }}</h2>
            <h2>{{ post.title }}</h2>
            <h3>{{ post.body }}</h3>
            <hr />
        </div>
    </div>
</template>

<script lang="ts">
import axios, { type AxiosResponse } from "axios";
import { defineComponent } from 'vue';
type DataPosts = {
    userId: number;
    id: number;
    title: string;
    body: string;
}
export default defineComponent({
    name: 'Articles',
    /*created() {
        this.getPosts()
    },*/
    data() {
        return {
            posts: [],
            errorMsg: '',
        }
    },
    methods: {
        getPosts() {
            axios.get<DataPosts[]>('https://jsonplaceholder.typicode.com/posts')
                .then((response: AxiosResponse) => {
                    console.log(response.data)
                    this.posts = response.data
                })
                .catch((error: string) => {
                    console.log(error)
                    this.errorMsg = error
                })
        }
    }
})
</script>

<style scoped>

</style>
