<script setup>
import {ArrowRightIcon} from "@heroicons/vue/outline";

const skills = [
	{
		title: 'Web開發',
		description: '開發網頁、網站、網路應用程式。',
	},
	{
		title: '資訊安全',
		description: '抓漏洞、未來協助大公司',
	},
	{
		title: '很會數學',
		description: '1到10年級數學A+',
	},
	{
		title: '很會打電動',
		description: '幾乎每一場PUBG都是MVP',
	},
	{
		title: '國文爛',
		description: '一篇300字文章都寫不出來',
	},
]
</script>

<template>

	<section id="about" class="pt-32 md:px-16 bg-green-800">
		<div class="flex flex-col md:flex-row justify-between items-center md:px-8 md:mb-4">
			<h1 class="text-2xl md:text-4xl text-white font-bold flex flex-col items-center">
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
					class="px-10 sm:px-20 py-3 sm:py-6 shadow-lg w-11/12 mx-auto bg-gray-200 rounded z-20 relative">
					<h4 class="font-extrabold text-black text-lg text-center mb-2 ">{{ skill.title }}</h4>
					<p class="text-black text-lg text-center mb-2">{{ skill.description }}</p>
				</div>
			</div>
		</div>
	</section>
</template>