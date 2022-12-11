<template>
	<div class="wrapper">
		<div class="block town center">
            <div class="title">Как с нами связаться?</div>
      </div>
		<div class="block double dark ">
			<div class="map">
				<div class="title__map">
				<p class="big">Где мы находимся?</p>	
					<p>Город Алматы, Абая 8а</p>
				</div>
				<div class="map__body">
					<img src="@/style/image/find.jpg" alt="">
				</div>
			</div>
			<div class="information">
				<div class="info">
					<div class="title__contact">Оставьте заявку</div>
					<div class="form">
						<div class="form__body">
							<form @submit.prevent="contactUs">
								<div class="item">

									<input type="text" required>
									<label for="">Введите имя</label>
								</div>
								<div class="item">
									<input type="text" required>
									<label for="">Введите телефон</label>
								</div>
								<div class="item">
									<input type="mail" required>
									<label for="">Введите почту</label>
								</div>
								<div class="item">
									<input type="submit">
								</div>
							</form>
						</div>
					</div>

				</div>
			</div>
		</div>
	</div>
</template>
<script>
export default {
    name: "contact_block"
}
</script>
<style scoped lang="scss">
$main_color: #d9730d;
.information {
	width: 1600px;
	margin: 0 auto;
	height: 800px;
	display: flex;
	justify-content: space-evenly;
}
.info {
	width: 90%;
	height: 100%;
	// background: rgb(224, 224, 224);
	padding: 20px;
	display: flex;
	.title__contact {
		width: 50%;
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		font-size: 60px;
	}
	.form {
		width: 50%;
		height: 100%;
		// background: #256;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		.item {
			display: flex;
			flex-direction: column;
			width: 600px;
			position: relative;
			label {
				position: absolute;
				top: 6px;
				transition: all .3s ease-in;
			}
		}
		input {
			border: 0;
			border-bottom: 1px solid #fff;
			background: transparent;
			padding: 5px;
			// border-radius: 10px;
			margin: 0px 0px 35px 0px;
			transition: all .4s ease-in;
			&[type='submit']:hover {
				background: $main_color;
				border: 1px solid #fff;
				border-radius: 10px;
				border: 1px solid $main_color;
			}
			&[type='submit'] {
				border: 1px solid #fff;
				border-radius: 10px;
				border: 1px solid #fff;
			}
			&:focus {
				outline: none;
			}
			&:focus + label {
				top: -25px;
				font-size: 18px;
			}
			&:valid + label{
				top: -25px;
				font-size: 18px;
			}
		}
	}
}
.map {
		width: 100%;
		height: 600px;
		display: flex;
}
.big {
	font-size: 55px;
}
p {
	font-size: 18px;
}
.title__map {
	width: 50%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}
.map__body {
	width: 50%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding: 90px;
}
img {
	max-width: 100%;
}


</style>