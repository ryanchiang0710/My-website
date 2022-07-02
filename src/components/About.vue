<script setup>
import {ArrowRightIcon} from "@heroicons/vue/outline";

const skills = [
	{
		title: 'Web開發',
		description: '開發網頁、網站、網路應用程式。',
	},
	{
		title: '寫作',
		description: '寫作文章、網誌',
	},
	{
		title: '吹泡泡',
		description: '吹出一顆又一顆泡泡',
	},
	{
		title: '煮飯',
		description: '煮出美味佳餚',
	},
	{
		title: '種植物',
		description: '自己種東西來吃',
	},
]
</script>

<template>

	<section id="about" class="pt-32 md:px-16 bg-gray-800">
		<div class="flex flex-col md:flex-row justify-between items-center md:px-8 md:mb-4">
			<h1 class="text-2xl md:text-4xl text-white font-bold">
				關於我
			</h1>
			<button
				class="my-8 mr-3 border-b border-white pb-2 flex items-center text-xl text-white">
				所有經歷
				<ArrowRightIcon class="ml-1 w-5 h-5"/>
			</button>
		</div>
		<div class="flex flex-wrap justify-start">
			<div
				class="w-full md:w-1/3"
				v-for="skill in skills">
				>
				<div
					class="px-10 sm:px-20 py-3 sm:py-6 shadow-lg w-11/12 mx-auto bg-white rounded z-20 relative">
					<h4 class="text-gray-800 text-lg text-center mb-2">{{ skill.title }}</h4>
					<p class="text-gray-600 text-lg text-center mb-2">{{ skill.description }}</p>
				</div>
			</div>
		</div>
	</section>
</template>