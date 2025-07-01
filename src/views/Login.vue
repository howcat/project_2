<script setup>
import { ref } from "vue";
import api from "@/services/api";

const username = ref("");
const email = ref("");
const password = ref("");
const loggedIn = ref(false);
const userProfile = ref(null);

const register = async () => {
	try {
		const res = await api.post("/register", {
			username: username.value,
			email: email.value,
			password: password.value,
		});
		alert("註冊成功");
	} catch (err) {
		alert("註冊失敗");
	}
};

const login = async () => {
	try {
		const res = await api.post("/login", {
			email: email.value,
			password: password.value,
		});
		localStorage.setItem("token", res.data.token);
		loggedIn.value = true;
		getProfile();
	} catch (err) {
		alert("登入失敗");
	}
};

const getProfile = async () => {
	try {
		const res = await api.get("/me");
		userProfile.value = res.data;
	} catch (err) {
		alert("取得資料失敗");
	}
};
</script>

<template>
	<div class="p-6 max-w-xl mx-auto space-y-4">
		<h1 class="text-2xl font-bold">Vue3 Web API 測試</h1>

		<div v-if="!loggedIn" class="space-y-2">
			<input v-model="username" placeholder="Username" class="border p-2 w-full" />
			<input v-model="email" placeholder="Email" class="border p-2 w-full" />
			<input
				v-model="password"
				type="password"
				placeholder="Password"
				class="border p-2 w-full"
			/>

			<button @click="register" class="bg-blue-500 text-white px-4 py-2">註冊</button>
			<button @click="login" class="bg-green-500 text-white px-4 py-2">登入</button>
		</div>

		<div v-if="loggedIn && userProfile">
			<h2 class="text-xl font-semibold">使用者資料</h2>
			<pre>{{ userProfile }}</pre>
		</div>
	</div>
</template>

<style>
</style>
