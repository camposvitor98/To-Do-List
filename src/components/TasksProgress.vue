<template>
    <div class="tasks-progress">
        <span class="progress-value">{{ progress }}%</span>
        <div class="progress-bar" :style="{width: progress + '%'}"></div>
    </div>
</template>

<script>
export default {
	props: {
		progress: { type: Number, default: 100 }
	}
};
</script>

<style>
.tasks-progress {
	position: relative;
	width: 60%;
	border: 1px solid #ffffff;
	color: #ffffff;
	border-radius: 8px;
	margin-bottom: 15px;
	display: flex;
	flex-direction: column;
	align-items: center;
}

.progress-bar {
	position: absolute;
	border-radius: 8px;
	height: 100%;
	background-color: #3ab63e;
	align-self: flex-start;
}

.progress-value {
	z-index: 1;
	font-size: 1.3rem;
}
</style>
