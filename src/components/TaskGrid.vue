<template>
    <div class="task-grid">
		<transition-group name="fade" mode="out-in" class="grid">
				<template v-if="tasks.length">
						<Task v-for="(task, i) in tasks" :key="task.name" style="animation-duration: 0.5s"
							@taskDeleted="$emit('taskDeleted', i)"
							@taskStateChanged="$emit('taskStateChanged', i)"
							:task="task"></Task>
				</template>		
				<p v-else class="no-task" style="animation-duration: 0.5s">- Parabéns! Sua vida está em dia! -</p>
		</transition-group>
    </div>
</template>

<script>
import Task from './Task.vue';

export default {
	components: { Task },
	props: {
		tasks: { type: Array, required: true }
	}
};
</script>

<style>
.grid {
	display: flex;
	justify-content: center;
	flex-wrap: wrap;
}

.grid .task {
	margin: 10px;
}

.no-task {
	color: #c4bdbd;
	font-size: 1.5rem;
	border-bottom: 1.5px solid #c4bdbd;
}
</style>
