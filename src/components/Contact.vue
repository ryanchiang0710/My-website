<script setup>
import {PhoneIcon, MailIcon} from '@heroicons/vue/outline';
import {ref} from "vue";
import axios from 'axios'
import Swal from 'sweetalert2'

const name = ref('');
const email = ref('');
const message = ref('');

const submit = () => {
	const access_key = 'd0df56ee-46d1-4c70-a00d-f6db65e8f669'
	axios.post('https://api.web3forms.com/submit', {
		access_key,
		email: email.value,
		name: name.value,
		message: message.value
	}).then(res => {
		if (res.status === 200) {
			Swal.fire({
				title: '感謝您的來信',
				text: '我們會盡快回覆您',
				icon: 'success',
				confirmButtonText: '確定'
			})
		}
	})
}
</script>
<template>
	<div id="contact" class="flex flex-col lg:flex-row bg-gray-800 pt-32 md:pb-32 md:px-20" :style="{'background-image':'url(https://www.internationalcitizens.com/wp-content/uploads/2019/12/maildelivery2.jpg)'}">
		<div class="py-10 lg:w-2/5 text-white px-8 xl:px-0 flex flex-col gap-4">
			<h1 class="text-4xl font-bold">聯絡我</h1>
			<p class="text-xl font-bold lg:pr-4 text-blue-300">
				晚上十點以後不要打給我因為我睡拉!
			</p>
			<div>
				<div class="flex items-center gap-4">
					<div>
						<PhoneIcon class="w-6 h-6"/>
					</div>
					<p class="font-bold">0963-612-277</p>
				</div>
				<div class="flex items-center gap-4 mt-3">
					<div>
						<MailIcon class="w-6 h-6"/>
					</div>
					<p class="font-bold">ryanchiang0710@gmail.com</p>
				</div>
			</div>
		</div>
		<div class="bg-gray-500 h-full lg:w-3/5 p-3 rounded-t-xl md:rounded-xl">
			<div class="bg-white py-4 px-8 rounded-xl">
				<h1 class="text-4xl text-gray-800 font-extrabold mb-6">聯絡表單</h1>
				<form class="block w-full flex flex-col items-start" @submit.prevent="submit">
					<label
						class="text-gray-800 text-sm font-bold"
						for="name">名字</label>
					<input id="name"
					       type="text"
					       class="w-full focus:outline-none focus:border focus:border-indigo-700 font-normal h-10 flex items-center pl-3 text-sm border-gray-300 rounded border"
					       placeholder="您的名字"
					       v-model="name"
					/>

					<label class="text-gray-800 text-sm mt-4 font-bold"
					       for="Email">電子郵件</label>
					<input id="Email"
					       type="email"
					       class="w-full focus:outline-none focus:border focus:border-indigo-700 font-normal h-10 flex items-center pl-3 text-sm border-gray-300 rounded border"
					       placeholder="您的電子郵件"
					       v-model="email"
					/>

					<label class="text-gray-800 text-sm mt-4 font-bold"
					       for="message">你要講什麼</label>
					<textarea id="message"
					          class="w-full border-gray-300 border mb-4 rounded py-2 text-sm outline-none resize-none px-3 focus:border focus:border-indigo-700"
					          placeholder="你要講什麼"
					          rows="8"
					          v-model="message"
					></textarea>

					<button
						class="self-center bg-gray-800 hover:bg-indigo-600 rounded text-white px-8 py-3 text-sm font-bold">
						送出
					</button>
				</form>
			</div>
		</div>
	</div>
</template>
