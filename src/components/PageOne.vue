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
.wrapper {
    position: relative;
    height: 950px;
    margin-left: 40px;
    background-image: url(../assets/Lines.svg);
    background-repeat: repeat-x;
}
h3 {
    padding: 0;
    margin: 0;
    font-weight: 500;
    font-size: 20px;
    line-height: 28px;
    color: #808080;
}
h1 {
    margin-top: 20px;
    font-weight: 500;
    font-size: 80px;
    line-height: 85px;
    letter-spacing: -0.02em;
    color: #000000;
}
.form {
    cursor: pointer;
    position: absolute;
    bottom: 80px;
    min-width: 400px;
    background: #4120c5;
    width: 880px;
    height: 80px;
    border: none;

    font-size: 20px;
    line-height: 24px;
    text-align: center;
    color: #ffffff;
}
</style>
