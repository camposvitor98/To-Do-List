<template>
    <div class="new-task">
        <input v-model="name" @keydown.enter="add" type="text"
            class="form-element" placeholder="Nova tarefa?">
        <button class="form-element" @click="add">+</button>
    </div>
</template>

<script>
export default {
	data() {
		return {
			name: ''
		};
	},
	methods: {
		add() {
			this.$emit('taskAdded', { name: this.name });
			this.name = '';
		}
	}
};
</script>

<style>
.new-task {
	margin: 35px;
}

.form-element {
	font-size: 1.25rem;
	outline: none;
	border: 1px solid #c4bdbd;
	padding: 5px 10px 8px;
	color: #c4bdbdaa;
}

input.form-element {
	background: #483d8baa;
	border-right: 0;
	border-radius: 6px 0 0 6px;
}

button.form-element {
	background: #4169e1;
	border-left: 0;
	border-radius: 0 6px 6px 0;
}
</style>
