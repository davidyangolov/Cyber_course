<template>
	<div class="wrapper">
		<div class="block town center">
            <div class="title">Наши курсы</div>
            <div class="subtitle">Развивайся. Обучайся. Живи</div>
      </div>
		<div class="block double dark ">
         <div class="container_courses">
				<div class="courses">
					<div class="item">
						<div class="img">
							<img src="https://static.tildacdn.com/tild3936-3632-4365-b566-613736653238/php.jpg" alt="php">
						</div>
						<div class="content">
							<div class="title_course">
								PHP
							</div>
							<div class="text">
								Объектно-ориентированый язык программирования, чаще используется на стороне сервера для обработки и передачи информации с базы данных
							</div>
							<div class="button">Подробнее о курсе</div>
						</div>
					</div>
					<div class="item">
						<div class="img">
							<img src="https://static.tildacdn.com/tild3936-3632-4365-b566-613736653238/php.jpg" alt="php">
						</div>
						<div class="content">
							<div class="title_course">
								PHP
							</div>
							<div class="text">
								Объектно-ориентированый язык программирования, чаще используется на стороне сервера для обработки и передачи информации с базы данных
							</div>
							<div class="button">Подробнее о курсе</div>
						</div>
					</div>
					<div class="item">
						<div class="img">
							<img src="https://static.tildacdn.com/tild3936-3632-4365-b566-613736653238/php.jpg" alt="php">
						</div>
						<div class="content">
							<div class="title_course">
								PHP
							</div>
							<div class="text">
								Объектно-ориентированый язык программирования, чаще используется на стороне сервера для обработки и передачи информации с базы данных
							</div>
							<div class="button">Подробнее о курсе</div>
						</div>
					</div>
					<div class="item">
						<div class="img">
							<img src="https://static.tildacdn.com/tild3936-3632-4365-b566-613736653238/php.jpg" alt="php">
						</div>
						<div class="content">
							<div class="title_course">
								PHP
							</div>
							<div class="text">
								Объектно-ориентированый язык программирования, чаще используется на стороне сервера для обработки и передачи информации с базы данных
							</div>
							<div class="button">Подробнее о курсе</div>
						</div>
					</div>
					<div class="item">
						<div class="img">
							<img src="https://static.tildacdn.com/tild3936-3632-4365-b566-613736653238/php.jpg" alt="php">
						</div>
						<div class="content">
							<div class="title_course">
								PHP
							</div>
							<div class="text">
								Объектно-ориентированый язык программирования, чаще используется на стороне сервера для обработки и передачи информации с базы данных
							</div>
							<div class="button">Подробнее о курсе</div>
						</div>
					</div>
					<div class="item">
						<div class="img">
							<img src="https://static.tildacdn.com/tild3936-3632-4365-b566-613736653238/php.jpg" alt="php">
						</div>
						<div class="content">
							<div class="title_course">
								PHP
							</div>
							<div class="text">
								Объектно-ориентированый язык программирования, чаще используется на стороне сервера для обработки и передачи информации с базы данных
							</div>
							<div class="button">Подробнее о курсе</div>
						</div>
					</div>
					<div class="item">
						<div class="img">
							<img src="https://static.tildacdn.com/tild3936-3632-4365-b566-613736653238/php.jpg" alt="php">
						</div>
						<div class="content">
							<div class="title_course">
								PHP
							</div>
							<div class="text">
								Объектно-ориентированый язык программирования, чаще используется на стороне сервера для обработки и передачи информации с базы данных
							</div>
							<div class="button">Подробнее о курсе</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
export default {
    name: "courses_block"
}
</script>
<style scoped lang="scss">
$main_color: #d9730d;
.courses {
	width: 1800px;
	margin: 150px auto;
	display: flex;
	justify-content: center;
	flex-wrap: wrap;
}
.item {
	width: 500px;
	height: 600px;
	border-top-left-radius: 15px;
	border-top-right-radius: 15px;
	overflow: hidden;
	margin-right: 55px;
}
.img {
	width: 100%;
	height: 300px;
	object-fit: cover;
}
.content {
	// border: 2px solid #fff;
	// border-top: none;
	background: rgb(40, 40, 40);
	padding: 15px;
	border-bottom-left-radius: 20px;
	border-bottom-right-radius: 20px;
}
.title_course {
	font-size: 35px;
	color: $main_color;
}
.text {
	font-size: 16px;
}
.button {
	border: 1px solid #fff;
	text-align: center;
	margin: 15px 0px 0px 0px;
	padding: 15px 0;
	border-radius: 10px;
	transition: all .4s ease-in-out;
	&:hover {
		background: #d9730d;
		border: 1px solid #d9730d;
		cursor: pointer;
	}
}

</style>