<template lang="html">
	<div class="users">
		<h1>Users</h1>
		<ul>
			<li v-for="user in users">
				{{ user.id }} - {{ user.name }} - {{ user.email }}
				<button v-on:click="deleteUser(user)">X</button>
			</li>
		</ul>
		<form v-on:submit.prevent="addUser">
			<input type="text" v-model="newUser.name" placeholder="Name">
			<input type="email" v-model="newUser.email" placeholder="Email">
			<button type="submit">
				Add
			</button>
		</form>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				users: [],
				newUser: {}
			}
		},
		methods: {
			addUser() {
				this.users.push(this.newUser)
				this.newUsers = {}
			},
			deleteUser(user) {
				this.users.splice(this.users.indexOf(user), 1)
			}
		},
		created() {
			this.$http.get('https://jsonplaceholder.typicode.com/users')
				.then(res => this.users = res.body)
		}
	}
</script>

<style>
	.users {
		background: #333;
		color: #fff;
		margin: 0;
		padding: 10px;
	}
	.users li {
		border-bottom: 1px solid darkgrey;
	}
	.users button {
		margin: 10px;
		border: none;
		outline: none;
		height: 40px;
		background: darkgrey;
		color: #fff;
		font-size: 18px;
		border-radius: 10px;
	}
	.users button:hover {
		background: rgba(0,0,0,.1);
	}
	.users input {
		border: none;
		border-bottom: 1px solid #fff;
		background: transparent;
		color: #fff;
		outline: none;
		height: 40px;
		font-size: 16px;
	}
</style>