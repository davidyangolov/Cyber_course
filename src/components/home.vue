<template>
    <div class="wrapper">
        <header>
            <div class="container">
                <div class="flex_menu">
                    <div class="logo"><img src="../style/icons/logo.png" alt="Кибер Курс"></div>
                    <div class="burger_menu">
                        <div class="burger"></div>
                    </div>
                    <nav>
                        <div class="menu__list">
                            <button class="menu__item" @click="showTabs" value="home">О компании</button>
                            <button class="menu__item" @click="showTabs" value="courses">Курсы</button>
                            <button class="menu__item" @click="showTabs" value="contact">Контакты</button>
                            <button class="menu__item" @click="openmodal" v-if="is_guest">Вход</button>
                            <button class="menu__item" @click="showTabs" value="profile" v-if="is_auth">{{user.login}}</button>
                        </div> 
                    </nav>
                </div>
            </div>
            <div class="top__btn">

            </div>
        </header>
        <main>
         <!-- home page    -->
        <div v-show="is_home">
            <div class="block town center">
                <div class="title">Кибер Курс</div>
                <div class="subtitle">Учение. Познание. Реализация.</div>
            </div>
            <div class="block dark">
                <div class="container">
                    <div class="title__advantages">Почему мы?</div>
                    <div class="advantages">
                        <div class="advantage__item">
                            <div class="backflip">
                                <div class="text">
                                    Есть возможность заниматься онлайн на разных площадках, а так же индивидуальные занятия в офлайн режиме
                                </div>
                            </div>
                            <div class="advantage__icon">
                                <ion-icon class="my_icon" name="shuffle"></ion-icon>
                            </div>
                            <div class="advantage__title">
                                Гибкость
                            </div>
                        </div>
                        <div class="advantage__item">
                            <div class="backflip">
                                <div class="text">
                                    Более 1000 студентов уже работают в крупных фирмах
                                </div>
                            </div>
                            <div class="advantage__icon">
                                <ion-icon class="my_icon" name="checkmark-circle"></ion-icon>
                            </div>
                            <div class="advantage__title">
                                Качество
                            </div>
                        </div>
                        <div class="advantage__item">
                            <div class="backflip top">
                                <div class="text">
                                    Есть курсы на любой бюджет, и на любые интересы
                                </div>
                            </div>
                            <div class="advantage__icon">
                                <ion-icon class="my_icon" name="cart"></ion-icon>
                            </div>
                            <div class="advantage__title">
                                Низкие цены
                            </div>
                        </div>
                        <div class="advantage__item">
                            <div class="backflip top">
                                <div class="text">
                                    Наши преподаватели имеют большой опыт преподавания, а так же опыт работы в своих сферах
                                </div>
                            </div>
                            <div class="advantage__icon">
                                <ion-icon class="my_icon" name="stats-chart"></ion-icon>
                            </div>
                            <div class="advantage__title">
                                Большой опыт
                            </div>

                        </div>

                    </div>
                </div>
             
            </div> 
            <div class="block triple light">
                  <div class="courses_programs">
                    <div class="title small">После любого курса Вы:</div>
                    <ul class="extrasmall">
                        <li>Сможете выстраивать и реализовывать алгоритмы</li>
                        <li>Разбираться в синтаксисе и структуре языка программирования</li>
                        <li>Работать с одним из лучших редакторов кода</li>
                        <li>Научитесь работать с системой GitHub</li>
                        <li>Разберетесь с основами Объектно-ориентированого программирования</li>
                        <li>Соберете портфолио для будущей работы</li>
                    </ul>
                  </div>
                  <div class="created">
                    <div class="title small">Об основателе</div>
                    <div class="created_by">
                        <div class="portrait">
                        <img src="../style/image/portrait.jpg" alt="Основатель онлайн школы">
                    </div>
                    <div class="description">
                        <p>Янголов Давид - основал школу Кибер Курс в 2022 году</p>                        
                        <p>Закончил «Университет Международного Бизнеса» имени Кенежегали Сагадиева по специальности информационные системы</p>
                        <p>Имеет опыт работы full-stack программистом и аналитиком в крупных торговых компаниях </p>
                        <p>Является преподавателем курса «Базы данных MySQL»</p>
                     </div>
                    </div>
                </div>
            </div>
           
         </div>
         <courses_block v-show="is_courses"></courses_block>  
        <!--  home page  --> 
        </main>
    
        <footer>
            <div class="social">
                <div class="items">
                    <ion-icon class="my_icon phone white" name="call"></ion-icon>
                    <div>
                        <a href="https://api.whatsapp.com/send?phone=87476056616" target="_blank">8 (747) 605 66 16</a>
                    </div>
                </div>
                <div class="items">
                    <ion-icon class="my_icon white" name="logo-instagram"></ion-icon>
                    <div><a href="https://instagram.com/davidyangolov" target="_blank">@davidyangolov</a></div>
                </div>
                <div class="items">
                     <ion-icon class="my_icon white" name="logo-vk"></ion-icon>
                    <div><a href="https://vk.com/yangolov" target="_blank">Давид Янголов</a></div>
                   
                </div>
                <div class="items">
                    <ion-icon class="my_icon white" name="mail"></ion-icon>
                    <div><a href="mailto:davidjangolov@mail.ru" target="_blank">davidjangolov@mail.ru</a> </div>
                    
                </div>
            </div>
        </footer>
    </div>
    <modal_regis_authorization @close="close" @auth="auth" @regis="regis" :class="{show: is_login}"></modal_regis_authorization>
</template>
<script>

import courses_block from '@/components/courses.vue'
import modal_regis_authorization from '@/components/modal.vue'
export default {
    name: "home_page",
    data: () => ({
        is_contact: false,
        is_courses: false,
        is_news: false,
        is_home: true,
        is_login: false,
        is_auth: false,
        is_guest: true,
        user: {}    
    }),
    components: {
        courses_block,
        modal_regis_authorization
    },
    methods: {
        showTabs(event) {
            let value = event.target.value
            switch (value) {
                case "home":
                    this.closeTabs()
                    this.is_home = true
                    break
                case "courses":
                    this.closeTabs()
                    this.is_courses = true
                    break
                case "news":
                    this.closeTabs()
                    this.is_news = true
                    break
                case "contact":
                    this.closeTabs()
                    this.is_contact = true
                    break
            }
        },
        openmodal() {
            this.is_login = true
            document.body.style.overflow = 'hidden'
        },
        closeTabs() {
        this.is_contact = false,
        this.is_courses = false,
        this.is_news = false,
        this.is_home = false
        },
        close(value) {
            this.is_login = value
            document.body.style.overflowY = 'auto'
        },
        auth(array) {
            if (array != null) {
                this.user = array
                this.is_auth = true
                this.is_guest = false
                console.log('succesfull');
                console.log(array);
            }
            else {
                this.is_guest = true
                console.log('failed');
            }
        },
        logout() {
            this.is_guest = true
        },
        regis(login) {
            console.log(login);
        }
    },
mounted() {


}
}

</script>
<style scoped lang="scss">
$main_color: #d9730d;

.container {
    overflow-x: hidden;
    .flex_menu {
        display: flex;
        align-items: center;
        justify-content: space-around;
        padding: 10px 5px;
        .logo {
            width: 150px;
            height: 100px;
            padding: 5px 15px;
        }
    }
}
.menu__item {
    margin-right: 15px;
    padding: 5px;
    background: none;
    border: 0;
    transition: color .3s ease-in-out;
    &:hover {
        cursor: pointer;
        color: $main_color;
    }
}
.advantages {
    margin-top: 150px;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
}

.title__advantages {
    padding-top: 200px;
    font-size: 50px;
    color: $main_color;
    text-align: center;
}
.advantage__item {
    width: 250px;
    height: 210px;
    display: flex;
    position: relative;
    flex-direction: column;
    justify-content: space-evenly;
    perspective-origin: 600px;
    border: 1px solid $main_color;
    background: rgb(33, 33, 33);
    padding: 5px;
    transition: all .7s ease-in-out;
    overflow: hidden;
    border-radius: 10px;
    &:hover {
    box-shadow: 0 0 25px $main_color;
    }
}
.advantage__item:hover  .backflip {
    transform: translate(0, 0)  rotate(0)  scale(1);
    opacity: 1;        
}
.backflip {
    width: 100%;
    height: 100%;
    position: absolute;
    transform: translate(-100%, 100%) rotate(45deg) scale(2);
    top: 0;
    left: 0;
    opacity: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background: $main_color;
    border-radius: 10px;
    transition: all .5s ease-in-out;
    z-index: 2;
    
    .text {
        font-size: 19px;
        text-align: center;
    }
}
// .backflip.top {
//     transform: translate(100%, 100%) rotate(-45deg);
// }
a {
    text-decoration: none;
}
.advantage__icon {
    margin-top: -25px;
    text-align: center;
}
.my_icon {
    color: $main_color;
    font-size: 40px;
}
.advantage__title {
    font-size: 25px;
    margin-top: -35px;
    text-align: center;
}
.menu__item:last-child {
    margin: 0;
}
.small {
    font-size: 60px;
    text-align: center;
}
.extrasmall {
    font-size: 40px;
    width: 900px;
    margin: 100px auto;
    text-align: left;
}
li {
    margin-bottom: 15px;
    margin-left: 20px;
    padding-left: 15px;
    position: relative;
}
a {
    color: #fff;
    transition: all .4s ease-in;
}
a:hover {
    color: #ff6922;
}
.social {
    width: 1300px;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
    justify-content: space-between;
}
.social * {
    font-size: 25px;
}
.social .items {

height: 80px;
padding: 0 10px;
display: flex;
align-items: center;
margin: 0 -15px 0 -15px;
}
.social .my_icon {
    margin-right: 5px;
    margin-left: 5px;
}
.white {
    color: #fff;
}
li::before {
    content: '✓';
    position: absolute;
    top: -9px;
    color: #d9730d;
    font-size: 34px;
    left: -15px;
}
.created_by {
    width: 1200px;
    margin: 15px auto;
    display: flex;
    padding: 20px 50px;
}
.portrait {
width: 35%;
height: auto;
border-radius: 15px;
overflow: hidden;
margin-right: 25px;
transition: all .4s ease-in-out;
}
img {
    object-fit: cover;
}
.description {
    width: 65%;
    font-size: 35px;
    padding: 0 20px;
}
p {
    font-size: inherit;
    text-indent: 45px;
}
.burger {
    width: 60px;
    height: 2px;
    background: #000;
    position: relative;
    display: none;
    &::after {
    content: '';
    width: 60px;
    height: 2px;
    background: #000;
    position: absolute;
    top: -10px;
    }
    &::before {
    content: '';
    width: 60px;
    height: 2px;
    background: #000;
    position: absolute;
    top: 10px;
    }
}
.my_icon {
    padding-top: 5px;
}
.phone {
    padding: 0;
}

</style>
