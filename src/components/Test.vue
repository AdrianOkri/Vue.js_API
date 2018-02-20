<template>
	<div class="test">
		{{ msg }}
	</div>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hola Vue.js',
				user: {
					firstName: 'Joe',
					lastName: 'McMillann'
				},
				myHtml: '<h3>Hola vue</h3>',
				showName: true,
				tasks: [
					{title: '1- eat'},
					{title: '2- dinner'},
					{title: '3- play'}
				]
			}
		},
		methods: {
			saludar(name) {
				alert(name)
			},
			typedEnter (ev) {
				console.log('DIO UN ENTER')
			}
		},
		computed: {
			fullName() {
				return this.user.firstName + ' ' + this.user.lastName;
			}
		},
		props: {
			msg: {
				type: String,
				default: 'Mensaje por defecto'
			}
		}
	}
</script>

<style media="screen">
	.test {
		background: #eee;
	}
</style>