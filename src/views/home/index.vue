<script setup>
import { ref, onMounted } from "vue";
const menu = ref();
const menuBtn = ref();


const MenuBtnFnc = () => {
    menu.value.classList.toggle("menu-open");
};

onMounted(() => {
    const counters = document.querySelectorAll('.counter')
    counters.forEach(counter => {
        counter.innerHTML = '0'
        let count = 0
        const updateCounter = () => {
            const target = parseInt(counter.dataset.count)
            if (count < target) {
                count += 50
                counter.innerHTML = count
                setTimeout(updateCounter, 10);
            } else {
                counter.innerHTML = target + '+'
            }
        }
        updateCounter()
    })
})

</script>

<template>
    <header>
        <div class="container">
            <nav class="navbar">
                <a href="#" class="brand">HouTouch</a>
                <ul class="menu" ref="menu">
                    <li><a href="#">首页</a></li>
                    <li><a href="#">详情</a></li>
                    <li><a href="#">关于我们</a></li>
                    <li><a href="#">联系我们</a></li>
                    <li class="btn-list-item">
                        <a href="#" class="btn btn-secondary">注销</a>
                    </li>
                    <li class="btn-list-item">
                        <a href="#" class="btn btn-primary">登录</a>
                    </li>
                </ul>
                <div class="buttons">
                    <a href="#" class="btn btn-secondary">注销</a>
                    <a href="#" class="btn btn-primary">登录</a>
                </div>
                <button class="menu-btn" @click="MenuBtnFnc()" ref="menuBtn">
                    <i class="fas fa-bars">123</i>
                </button>
            </nav>
            <div class="header-body">
                <div class="header-text">
                    <div>
                        <h1 class="title">
                            获取 A + 的体验<br />
                            你的产品
                        </h1>
                        <p>我们提供最优质的产品，让您的产品体验达到 A + 级别。</p>
                        <div class="buttons">
                            <a href="#" class="btn btn-primary">开启免费体验</a>
                            <a href="#" class="btn btn-secondary">关于我们</a>
                        </div>
                        <div class="stats">
                            <div>
                                <h2 class="counter" data-count="1200">1200+</h2>
                                <p>节日快乐</p>
                            </div>
                            <div class="line"></div>
                            <div>
                                <h2 class="counter" data-count="600">600+</h2>
                                <p>任务完成</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="banner">
                    <div class="img-frame">
                        <div class="first-img"></div>
                        <div class="second-img"></div>
                        <div class="three-img"></div>
                        <div class="four-img"></div>
                    </div>
                    <!-- <img src="../../assets/img/1.png" alt="" /> -->
                </div>
            </div>
        </div>
    </header>

    <section class="cards">
        <div class="container">
            <div class="card">
                <img src="@/assets/img/2.png" alt="" />
                <div class="card-text">
                    <h3>第一</h3>
                    <p>这是一段内容</p>
                    <a href="#">
                        查看更多
                        <i class="fas fa-arrow-right"></i>
                    </a>
                </div>
            </div>
            <div class="card">
                <img src="@/assets/img/3.png" alt="" />
                <div class="card-text">
                    <h3>第二</h3>
                    <p>这是一段内容</p>
                    <a href="#">
                        查看更多
                        <i class="fas fa-arrow-right"></i>
                    </a>
                </div>
            </div>
            <div class="card">
                <img src="@/assets/img/4.png" alt="" />
                <div class="card-text">
                    <h3>第三</h3>
                    <p>这是一段内容</p>
                    <a href="#">
                        查看更多
                        <i class="fas fa-arrow-right"></i>
                    </a>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
a {
    text-decoration: none;
    color: #000;
}

a:not(.btn-primary):hover {
    color: #6b6b6b;
}

p {
    margin: 1em 0;
}

ul {
    list-style: none;
}

.btn-primary {
    background: black;
    padding: 0.7em 1.5em;
    border-radius: 5px;
    color: #fff;
    margin: 0px 1em;
}

.container {
    max-width: 1250px;
    margin: 0 auto;
    padding: 0 2.5em;
}

header {
    margin-bottom: 4em;

    .container {
        display: flex;
        justify-content: flex-start;
        align-items: center;
        flex-direction: column;
        min-height: 100vh;
    }
}

.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 2em 0;
}

.brand {
    font-size: 1.5em;
}

.navbar .menu {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 3em;
}

.menu-btn {
    background: none;
    border: none;
    cursor: pointer;
    font-size: 1.5em;
    display: none;
}

.btn-list-item {
    display: none;
}

.header-body {
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    min-height: 80vh;
}

.header-body .btn {
    margin: 1em 1em 0em 0em;
    display: inline-table;
}

// .banner img {
//   width: 100%;
//   height: 100%;
//   animation: fadeIn 0.6s ease-in-out;
// }
.banner {
    width: 130%;
    height: 80%;

    .img-frame {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-content: stretch;
        justify-content: space-evenly;
        align-items: center;

        .first-img {
            width: 20%;
            height: 80%;
            border-radius: 5em;
            background-color: blanchedalmond;
            transform: rotate(10deg);
            background: url('@/assets/img/4.png');
            animation: fadeIn 0.6s ease-in-out;
        }

        .second-img {
            width: 20%;
            height: 80%;
            border-radius: 5em;
            background-color: blanchedalmond;
            margin-top: -4em;
            transform: rotate(10deg);
            background: url('@/assets/img/4.png') 20%;
            animation: fadeIn 0.8s ease-in-out;
        }

        .three-img {
            width: 20%;
            height: 80%;
            border-radius: 5em;
            margin-top: 6em;
            background-color: blanchedalmond;
            transform: rotate(10deg);
            background: url('@/assets/img/4.png') 40%;
            animation: fadeIn 1s ease-in-out;
        }

        .four-img {
            width: 20%;
            height: 80%;
            margin-left: 1em;
            margin-top: -8em;
            border-radius: 5em;
            background-color: blanchedalmond;
            transform: rotate(10deg);
            background: url('@/assets/img/4.png') 60%;
            animation: fadeIn 1.2s ease-in-out;
        }
    }
}

.title {
    font-size: 3em;
    margin: 0.4em 0;
    line-height: 60px;
    animation: slideUp 0.7s ease-in;
}

.header-text p {
    font-size: 1.1em;
    line-height: 27px;
    max-width: 450px;
}

.header-text .ben-primary {
    margin-right: 1em;
}

.stats {
    display: flex;
    align-items: center;
}

.stats>div {
    margin: 2em 2em 0 0;
}

.stats h2 {
    font-size: 2em;
}

.stats p {
    margin: 0;
    font-size: 0.9em;
}

.line {
    background: #000;
    margin: 0 1.5em;
    width: 3px;
    height: 3em;
}

.cards {
    margin-bottom: 2em;
}

.cards .container {
    padding: 2em;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    justify-items: center;
    grid-gap: 2em;
}

.cards img {
    width: 100%;
    border-radius: 2.5em;
    margin-top: -4em;
    transition: 0.3s;
}

.card {
    background: #ffffff;
    padding: 2em;
    border-radius: 2.5em;
}

.card-text {
    margin: 1.5em 1em 0 1em;
}

.card p {
    margin: 1em 0;
    font-size: 0.9em;
    line-height: 27px;
}

.card:hover img {
    transform: translateY(-2em);
}

.card a i {
    margin: 0 0.5em;
}

@keyframes fadeIn {
    0% {
        opacity: 0;
    }

    100% {
        opacity: 1;
    }
}

@keyframes slideUp {
    0% {
        transform: translateY(100px);
        opacity: 0;
    }

    100% {
        transform: translateY(0px);
        opacity: 1;
    }
}

@media screen and (max-width: 1000px) {
    .menu-btn {
        display: block;
    }

    .navbar .menu {
        background: #ffffff;
        box-shadow: 0em 1em 8em rgba(26, 26, 26, 0.1);
        position: absolute;
        left: 0;
        top: 6em;
        width: 100%;
        height: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        opacity: 0;
        transition: 0.6s;
        overflow: hidden;
        z-index: 9;
    }

    .btn-list-item {
        display: block;
    }

    .navbar {
        .buttons {
            display: none;
        }

        .menu {
            padding: 3em 0;
            flex-direction: column;
            justify-content: flex-start;
            overflow-y: scroll;
        }
    }

    .navbar .menu-open {
        opacity: 1;
        height: 30em;
        overflow: visible;
    }

    .header-body,
    .cards .container {
        grid-template-columns: 1fr;
    }

    .card {
        margin: 2em 0;
    }

    .banner {
        display: none;
    }
}
</style>
