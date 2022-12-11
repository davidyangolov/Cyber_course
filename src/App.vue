<template>
	<div class="wrapper">
		<home_page></home_page>
	</div>
</template>
<script>
import home_page from '@/components/home.vue'
export default {
	name: "App",
	components: {
		home_page
	}
}
</script><style lang="scss">
$_color: rgb(255, 255, 255);
$main_color: #d9730d;
*{
    text-shadow: 1px 10px 6px #000;
}
*, *::after, *::before {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    font-size: 25px;
    color: $_color;
    list-style: none;
    font-weight: 100;
}
.wrapper {
    display: flex;
    flex-direction: column;
    overflow-x: hidden;
    max-width: 100vw;
}
header {
flex: 0 0 100px;
background: #222;
}
main {
    flex: 0 1 100vh;
}
footer {
    flex: 0 1 100px;
    background: #222;
}
.container {
    width: 1224px;
    margin: 0 auto;
    overflow-x: hidden;
}
.block {
    min-height: 100vh;
    overflow-x: hidden;
}
.double {
    min-height: 200vh;
}
.triple {
    min-height: 300vh;
}
.town {
    background: url('@/style/image/town.jpg') center fixed;
    background-size: cover;
}
.dark {
   background: linear-gradient(rgb(34, 34, 34), rgb(15, 15, 15), rgb(0,0,0), rgb(15, 15, 15), rgb(34,34,34));
}
.light {
    background: linear-gradient(rgb(34, 34, 34), rgb(64, 64, 64), rgb(77, 77, 77), rgb(64, 64, 64),rgb(34, 34, 34));
}
.center {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.title {
    font-size: 100px;
    
    animation: animate .9s ease-in-out forwards;
}
.subtitle {
    font-size: 26px;
    text-shadow: 1px 5px 3px #000;
    animation: animate .9s ease-in-out forwards;
}
@keyframes animate{
from {
opacity: 0;
transform: translate(-25px, 0);
}
to {
    opacity: 1;
    transform: translate(0, 0);
}
}
img {
    width: 100%;
    height: 100%;
}
</style>