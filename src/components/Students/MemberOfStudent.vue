<script setup>

const props = defineProps(["groupPeople"])

</script>

<template>

	<div class="container">
		<div class="card" v-for="people in props.groupPeople" :class="people.group, people.type == null ? 'student' : 'assistant'">
		<div class="card-header">
			{{ people.name }}
		</div>
		<div class="card-body">
			{{ people.type == null ? "Student" : "Assistant" }}
		</div>
	</div>

	</div>

</template>

<style scoped>
	.container {
		display : grid;
		grid-template-columns: repeat(4,1fr);
		grid-gap: 1rem;
	}
	.Orchid.student {
		border : 1px solid Orchid;
	}
	.Orchid.assistant {
		border : 1px solid Orchid;
		background-color: Orchid;
		color: white;
	}
	.SteelBlue.student {
		border : 1px solid SteelBlue
	}
	.SteelBlue.assistant {
		border : 1px solid SteelBlue;
		background-color: SteelBlue;
		color: white;
	}
	.IndianRed.student {
		border : 1px solid IndianRed
	}
	.IndianRed.assistant {
		border : 1px solid IndianRed;
		background-color: IndianRed;
		color: white;
	}
	.YellowGreen.student {
		border : 1px solid YellowGreen
	}
	.YellowGreen.assistant {
		border : 1px solid YellowGreen;
		background-color: YellowGreen;
		color: white;
	}
	.LightSeaGreen.student {
		border : 1px solid LightSeaGreen
	}
	.LightSeaGreen.assistant {
		border : 1px solid LightSeaGreen;
		background-color: LightSeaGreen;
		color: white;
	}
	</style>