<script setup>
import {ArrowRightIcon, ChevronDoubleDownIcon} from '@heroicons/vue/solid'
</script>
<template>
	<section class="flex flex-col justify-center items-center md:px-20 min-h-screen" :style="{'background-image':'url(https://th.bing.com/th/id/OIP.l-7ci-qyVMc6vvCMlOHBQQHaEo?pid=ImgDet&rs=1)'}">
		<div class="flex flex-col w-full py-12 px-4 lg:px-0 justify-center items-center">
			<p class="text-4x1 text-green-800 font-bold">我是<span class="text-blue-400">江承恩</span></p>
			<h1 class="text-6xl items-center justify-center text-white mt-1 font-extrabold">
				一個喜歡資訊安全的高中生
			</h1>
			<p class="text-lg text-white font-bold pt-8">
				<a href="#about" >[關於我]</a>
			</p>
			<a
				href="#contact"
				class="mt-3 flex items-center text-xl font-bold pb-2 text-gray-400">
				聯絡我
				<ArrowRightIcon class="ml-1 w-5 h-5"/>
			</a>
		</div>

		<a href="#activities" class="animate-bounce cursor-pointer">
			<chevron-double-down-icon class="w-16 h-16"/>
		</a>
	</section>
</template>
