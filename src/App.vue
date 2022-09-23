<script setup>
	import { onMounted, ref } from 'vue'
	import MainComponent from './components/MainComponent.vue'
	import DATA from './assets/data/data.json'
	import MemberOfStudent from './components/Students/MemberOfStudent.vue'
	
	const allData = ref([]);
	const groupNames = ref([]);
	const groupPeople = ref([]);
	const getData = async (data) => {
		allData.value = await data;
		}
	
	const getNamesOfGroups = async (data) => {
		const names_of_groups = await data.map(data_of_student => data_of_student.group)
		const unique_names_of_groups = [...new Set(names_of_groups)]
		groupNames.value = unique_names_of_groups;
		console.log(groupNames.value)
	}
	
	const filterByGroupNames = (groupName) => {
		groupPeople.value = allData.value.filter(people => people.group === groupName)
	}
	
	onMounted( () => {
		getData(DATA)
		getNamesOfGroups(DATA)
	});
	</script>
	
	<template>
	
	<MainComponent :groupNames="groupNames" @getPeople="filterByGroupNames"/>
	<MemberOfStudent :groupPeople="groupPeople"/>
	
	</template>
