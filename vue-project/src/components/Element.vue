<template>
	<p v-if="!input">{{ text }}</p>
	<input v-else type="text" :value="text" @blur="modify($event)" ref="inputRef" />
	<button @click="remove()">Remove</button>
	<button @click="input = true">Modify</button>
</template>

<script lang="ts">

import { defineComponent } from 'vue';
export default defineComponent({
    name:'Element',
    props: ["index", "text"],
    emits: ["remove", "modify"],
    data() {
        return {
        	input: false
        }
    },
    methods: {
    	remove() {
    		this.$emit("remove", { index: this.index })
    	},
    	modify(event) {
    		let value = event.target.value;
    		this.input = false;
    		this.$emit("modify", { index: this.index, value: value })
    	}
    },
    updated() {
        if (this.$refs.inputRef) this.$refs.inputRef.focus();
    }
})
</script>

<style scoped>

</style>