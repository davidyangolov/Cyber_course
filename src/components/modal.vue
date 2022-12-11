<template>
	<div class="modal__body center">
		<div class="forms">
			<form @submit.prevent="auth" class="form_body auth"  :class="{visible: !is_active}">
			<div class="title__form">Авторизация</div>
			<div class="close" @click="close"></div>
			<div class="error">{{error}}</div>
			<div class="item">
			<label for="username">Имя пользователя:</label>
			<input type="text" id="username" placeholder="Введите логин..." v-model="login">
			</div>
			<div class="item">
			<label for="password">Пароль:</label>
			<input type="text" id="password" placeholder="Введите пароль..." v-model="password">
			</div>
			<div class="item row">
				<div>Еще нет аккаунта?</div> <div class="span" @click="toggle">Зарегистрируйтесь!</div>
			</div>
			<div class="item">
				<input type="submit" class="btn" value="Войти">
			</div>
		</form>
		<form @submit.prevent="regis" class="form_body regis" :class="{visible: is_active}">
			<div class="title__form">Регистрация</div>
			<div class="close" @click="close"></div>
			<div class="error">{{error}}</div>
			<div class="item">
			<label for="username1">Имя пользователя:</label>
			<input type="text" id="username1" placeholder="Введите логин..." v-model="login">
			</div>
			<div class="item">
			<label for="password1">Пароль:</label>
			<input type="text" id="password1" placeholder="Введите пароль..." v-model="password">
			</div>
			<div class="item">
			<label for="password1">Повторите пароль:</label>
			<input type="text" id="password1" placeholder="Повторите пароль..." v-model="repassword">
			</div>
			<div class="item row">
				<div>Уже есть аккаунт?</div> <div class="span" @click="toggle">Войдите!</div>
			</div>
			<div class="item">
				<input type="submit" class="btn" value="Зарегистрироваться">
			</div>
		</form>
		</div>
	</div>
</template>
<script>
import axios from 'axios'
export default {
    name: "modal_regis_authorization",
	data() {
		return {
			is_active: false,
			error: '',
			login: '',
			password: '',
			repassword: ''
		}
	},
	methods: {
		close() {
			this.$emit('close', false)
		},
		toggle() {
			this.is_active = !this.is_active
		},
		async auth() {
			const {data} = await axios.get('http://localhost/basic/web/index.php/api/get-users?login='+this.login)
			if (data == false) {
				this.error = 'Пользователь не найден'
			}
			else {
				this.$emit('auth', data)
				this.error = ''
				this.$emit('close', false)
			}

		},
		async regis() {
			if (this.repassword === this.password) {
				await axios.get('http://localhost/basic/web/index.php/api/regis-users?login='+this.login)
				this.error = ''
				this.$emit('close', false)

			}
			else {
				this.error = 'Пароли не совпадают'
			}
		}
	}
}
</script>
<style scoped lang="scss">
* {
	border: 0;
	background: 0;
	outline: none;
}
.item {
	width: 100%;
	display: flex;
	flex-direction: column;
	text-align: left;
	margin-bottom: 35px;
}
input {
	border: 1px solid #fff;
	padding: 15px;
	border-radius: 10px;
}
.modal__body {
	min-height: 100vh;
	opacity: 0;
	pointer-events: none;
	width: 100%;
	background: rgba(0, 0, 0, 0.614);
	position: absolute;
	top: 0;
	left: 0;
	text-align: center;

}
.modal__body.show {
	opacity: 1;
	pointer-events: all;
	
}

.close::before {
	content: '✖';
	position: absolute;
	top: 16px;
	right: 40px;
	z-index: 2;
	font-size: 40px;
	color: rgb(203, 0, 0);
}
.close:hover {
	cursor: pointer;
}
.close:hover::before {
	color: rgb(255, 0, 0);
	text-shadow: 0 0 15px #f00;
}
.forms {
	transform: translateY(150px);
	position: relative;
}
.regis {
	position: absolute;
	top: -700px;
	left: 0;
	opacity: 0;
	z-index: 4;
	pointer-events: none;
}
.auth {
	opacity: 0;
	pointer-events: all;
	z-index: 3;
}
.row {
	max-width: 100%;
	margin: 25px auto;
	margin-top: 0;
	padding: 15px 0;
	height: 50px;
}
.span {
	height: 50px;
	margin-left: -300px;
	transition: all .4s ease-in-out;
	
}
.regis .span {
	margin-left: -200px;
}
.span:hover {
	cursor: pointer;
	color: #ff6911;
}

.visible {
	opacity: 1;
	pointer-events: all;
}
.error {
	color: #f00;
}
.form_body {
	width: 900px;
	height: auto;
	background: #222;
	border-radius: 10px;
	padding: 25px;
	margin: 0 auto;
	position: relative;
	transform: translateY(100%);
	transition: transform .4s ease-in-out, opacity .2s ease-in-out;
	display: flex;
	flex-direction: column;
	justify-content: space-evenly;
}
label {
	cursor: pointer;
	margin-bottom: 10px;
}
::placeholder {
	opacity: 0;
	transition: all .4s ease-in-out;
}
input:focus::placeholder {
	opacity: 1;
}
.btn {
transition: all .4s ease-in-out;
color: #fff;
}
.btn:hover {
	background-color: #ff6911;
	cursor: pointer;
	border: 1px solid #ff6911;
}
.modal__body.show  .form_body {
	transform: translateY(0);
}
.form_body .title__form {
	font-size: 35px;
}
</style>