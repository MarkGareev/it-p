<template>
    <div class="wrapper">
        <h3>Род деятельности компании</h3>
        <h1>
            Поставка компьютерного <br />
            оборудования российских <br />
            и зарубежных производителей
        </h1>
        <button class="form" @click="goToPage">Заказать звонок</button>
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
.wrapper {
    margin-left: 40rem;
    padding-right: 40rem;
    padding: 50rem 40rem 50rem 0;

    position: relative;
    height: 100vh;
    background-image: url(../assets/Lines.svg);
    background-repeat: repeat;

    @media (min-width: 1920px) {
        background-size: 100% auto;
    }
    @media (max-width: 768px) {
        background-size: 100%;
        height: 1000rem;
    }
    @media (max-width: 425px) {
        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: max-content max-content 1fr;
        height: calc(100vh - 60rem);
        margin-left: 0;
        padding: 30rem 20rem;

        background-image: url(../assets/BackgroundMobile.svg);
    }
}
h3 {
    font-weight: 500;
    font-size: 20rem;
    line-height: 28rem;
    color: #808080;
    @media (max-width: 425px) {
        font-size: 10rem;
        line-height: 12rem;
    }
}
h1 {
    margin-top: 20rem;
    font-weight: 500;
    font-size: 80rem;
    line-height: 85rem;
    letter-spacing: -0.02em;
    color: #000000;
    @media (max-width: 425px) {
        font-size: 35rem;
        line-height: 114%;
    }
}
.form {
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

    @media (min-width: 1920px) {
        width: 62.95%;
    }
    @media (max-width: 1255px) {
        width: 440px;
    }
    @media (max-width: 768px) {
        width: 62.95%;
    }
    @media (max-width: 425px) {
        width: 100%;
        position: unset;
        align-self: end;
        font-size: 14rem;
        line-height: 17rem;
        height: 60rem;
    }
}
</style>
