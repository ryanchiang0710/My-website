<script setup>
import {ArrowRightIcon} from '@heroicons/vue/outline';

const activities = [
	{
		title: '社交工程',
		description: '前往',
		url: 'https://www.youtube.com/watch?v=dQw4w9WgXcQ&ab_channel=RickAstley'
	},
	{
		title: '資安的重要性',
		description: '現在的科技時代，需要資安的存在'
	}
]
const makeClass = (i) => (
	i % 2 === 0 ?
		"flex flex-col sm:flex-row items-stretch mb-8 sm:mb-16 container mx-auto" :
		"flex flex-col sm:flex-row-reverse items-stretch mb-8 sm:mb-16 container mx-auto"
)
</script>
<template>
	<section id="activities" class="pt-32 px-2 md:px-20">
		<template v-for="(activity,i) in activities">
			<div :class="makeClass(i)">
				<div class="w-full sm:w-1/2 relative h-64 sm:h-auto">
					<img alt="活動圖片" class="w-full object-cover absolute inset-0 object-center h-full"
					     loading="lazy" :src="activity.image ?? 'https://rockyknolltech.com/wp-content/uploads/sites/725/2021/03/bigstock-Cyber-Security-Data-Protection-398556191-scaled.jpg'"/>
				</div>
				<div
					class="container mx-auto w-full sm:w-1/2 py-8 sm:py-16 lg:py-32 px-6 sm:px-12 lg:px-24 bg-gray-200">
					<h3 class="text-gray-800 text-2xl mb-3 leading-normal tracking-normal font-bold">{{
							activity.title
						}}</h3>
					<p class="text-gray-600 leading-6 font-normal tracking-normal mb-6">
						{{ activity.description }}
					</p>
					<a
						v-if="activity.url"
						:href="activity.url"
						target="_blank"
						class="focus:outline-none rounded py-3 px-4 text-black border border-black flex justify-center items-center text-base hover:bg-blue-200 bg-transparent">
						社交工程範例
					</a>
				</div>
			</div>
		</template>

		<div class="mb-16 sm:mb-32 container mx-auto px-6 container">
			<button
				class="focus:outline-none my-8 flex items-center text-xl font-regular border-b border-black pb-2 mr-3">
				<a href="https://www.comptia.org/content/articles/why-is-cybersecurity-important#:~:text=So%20much%20has%20been%20written%20about%20cybersecurity%20that,we%20use%20every%20day%2C%20we%20are%20living%20online." target="_blank">了解資安的重要性</a>
				<ArrowRightIcon class="ml-1 w-5 h-5"/>
			</button>
		</div>
	</section>
</template>
