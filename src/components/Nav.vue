<script setup>
import {MenuIcon, XIcon} from '@heroicons/vue/solid'
import {ref} from "vue";

const mobileMenu = ref(false)
const toggleMenu = () => mobileMenu.value = !mobileMenu.value
</script>
<template>
	<header class="mx-auto px-4 bg-gray-200 fixed w-full z-50 flex items-center justify-center rounded border">
		<a href="#" :class="{hidden: mobileMenu}">
			<img class="w-16" loading="lazy" src="../assets/OIP.jpg" alt="MyLogo"/>
		</a>
		<div
			:class="
				!mobileMenu ?
					'block md:hidden text-gray-500 relative z-30 top-0' :
					'block md:hidden text-gray-500 relative z-30 top-0 flex justify-center w-full py-4'
			"
			@click="toggleMenu">
			<MenuIcon class="h-8 w-8" v-if="!mobileMenu"/>
			<XIcon class="h-8 w-8" v-if="mobileMenu"/>
		</div>
		<div id="menu" :class="{hidden: !mobileMenu, 'md:block': true}">
			<ul class="text-3xl md:text-base flex flex-col md:flex-row justify-center items-center fixed md:relative md:pr-10 top-0 bottom-0 left-0 right-0 bg-gray-200 z-20">
				<li class="font-extrabold md:mr-10 flex items-center text-gray-800 hover:text-blue-800 pt-10 md:pt-0">
					<a href="#activities"
					   @click="mobileMenu = false"
					>了解資安</a>
				</li>
				<li class="font-extrabold md:mr-10 flex items-center text-gray-800 hover:text-blue-800 pt-10 md:pt-0">
					<a href="#about"
					   @click="mobileMenu = false">我會的東西</a>
				</li>

				<li class="font-extrabold md:mr-0 flex items-center text-gray-800 hover:text-blue-800 pt-10 md:pt-0">
					<a href="#contact"
					   @click="mobileMenu = false">聯絡我</a>
				</li>
			</ul>
		</div>
	</header>
</template>
