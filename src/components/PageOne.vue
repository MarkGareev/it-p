<template>
    <div class="wrapper">
        <h3>Род деятельности компании</h3>
        <h1>
            Поставка компьютерного <br />
            оборудования российских <br />
            и зарубежных производителей
        </h1>
        <button class="form" @click="goToPage">Форма обратной связи</button>
    </div>
</template>
<script>
import listItemVue from "./listItem.vue";
export default {
    name: "PageOne",
    methods: {
        goToPage(links) {
            document.querySelector(`#footer`).scrollIntoView({
                behavior: "smooth",
            });
        },
    },
};
</script>
<style lang="scss">
@media (min-width: 1920px) {
    .wrapper {
        background-size: 100% auto;
    }
    .form {
        width: 62.95% !important;
    }
}

@media (max-width: 1255px) {
    .form {
        width: 440px !important;
    }
}

.wrapper {
    padding-right: 40rem;

    position: relative;
    height: 100vh;

    margin-left: 40rem;
    background-image: url(../assets/Lines.svg);
    background-repeat: repeat;
}
h3 {
    padding: 0;
    margin: 0;
    font-weight: 500;
    font-size: 20rem;
    line-height: 28rem;
    color: #808080;
}
h1 {
    margin-top: 20rem;
    font-weight: 500;
    font-size: 80rem;
    line-height: 85rem;
    letter-spacing: -0.02em;
    color: #000000;
}
.form {
    // margin-right: 80px;
    height: 80rem;
    width: 880px;

    position: absolute;
    bottom: 50rem;

    cursor: pointer;
    background: #4120c5;
    border: none;
    font-size: 20rem;
    line-height: 24rem;
    text-align: center;
    color: #ffffff;
}
</style>
