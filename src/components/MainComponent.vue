<script setup>

const props = defineProps(["groupNames"])
const emits = defineEmits(["getPeople"])
const getPeople = (group) => {
		emits("getPeople", group)
}

</script>

<template>
	
	<div class="container">
		<ul class="group-list">
			<li v-for="group in props.groupNames" @click="getPeople(group)">
				{{group}}
				
			</li>
		</ul>
			
	</div>

</template>

<style scoped>
	.group-list {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		align-items: center;
		gap: 8px;
	}

	.group-list li {
		border: 1px solid white;
		cursor: pointer;
		padding: 8px;
	}
</style>
