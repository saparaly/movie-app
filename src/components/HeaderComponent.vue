<script></script>

<template>
    <header class="header">
        <div class="container">
            <div class="header__container">
                <RouterLink to="/" class="logo">
                    <img alt="logo" src="@/assets/logo.svg" width="106" height="20" />
                </RouterLink>
                <ul class="header__links">
                    <li class="header__link"><RouterLink to="/">Фильмы 2022</RouterLink></li>
                    <li class="header__link"><RouterLink to="/">Сериалы 2022</RouterLink></li>
                </ul>
                <ul class="header__box">
                    <!-- <li class="header__box-item">
                        <form action="">
                            <input type="text">
                            <button>search</button>
                        </form>
                    </li> -->
                    <li class="header__box-item"><a href="">ava</a></li>
                    <li class="header__box-item">RU</li>
                </ul>
            </div>
        </div>
    </header>
</template>

<style scoped>
.header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 35px 0;
    /* background: #333; */
    z-index: 50;
}

.header__container{
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.header__links, .header__box {
    display: flex;
    align-items: center;
}
.header__link{
    margin-left: 40px;
}
.header__box-item  {
    margin-left: 24px; 
}
.header__link:first-child, .header__box-item:first-child{
    margin-left: 0;
}
</style>