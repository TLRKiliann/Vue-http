<template>
    <div>
        <h2>Todo List</h2>
        <button @click="add()">Add a new Element</button>
        <Element v-for="(element, index) in elements" :key="index" 
            :text="element" :index="index"
            @remove="remove($event)"
            @modify="modify($event)"
        />
    </div>
</template>

<script lang="ts">
import Element from "./Element.vue";
import { defineComponent } from 'vue';
export default defineComponent({
    name:'TodoList',
    components: {
        Element: Element
    },
    data() {
        return {
            elements: []
        }
    },
    methods: {
        add() {
            let element = "Element " + (this.elements.length + 1);
            this.elements.push(element);
        },
        remove(params) {
            let index = params.index;
            this.elements.splice(index, 1);
        },
        modify(params) {
            let index = params.index;
            let value = params.value;
            this.elements[index] = value;
        }
    }
})
</script>

<style scoped>

</style>
