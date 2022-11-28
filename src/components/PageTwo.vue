<template>
    <div class="wrapperTwo">
        <h3 class="pageTwoH3">Компания</h3>
        <listItem :list="getList" />
        <div class="tenders">
            <a href="https://www.rusprofile.ru/id/7295048" target="_blank"
                >Смотреть тендеры</a
            >
        </div>
        <div></div>
    </div>
</template>
<script>
import listItem from "./listItem";
export default {
    name: "PageTwo",
    components: {
        listItem,
    },
    data() {
        return {
            show: false,
            isDesctop: true,
        };
    },
    computed: {
        getList() {
            return [
                {
                    title: this.isDesctop
                        ? "История создания компании"
                        : "О компании",
                    text: "Компания была создана в 2014 г. в Перми путём объединения ИТ-специалистов, имевших к этому времени широкий опыт работы на рынке Приволжского федерального округа. Нацеленность на сотрудничество с государственными и корпоративными заказчиками позволила ещё больше расширить собственные компетенции, добавила бесценного опыта  и обеспечила устойчивое развитие.",
                },
                {
                    title: this.isDesctop
                        ? "Государственные тендеры"
                        : "Гос.тендеры",
                    text: "Тесное сотрудничество со многими производителями высокотехнологичных решений дало возможность компании стать победителем в более или выступить, чем 100 государственных и коммерческих тендеров на общую сумму более 1 млрд. руб.",
                },
                {
                    title: "Преимущества",
                    text: "Компетентность и ответственность - основные преимущества нашей компании.",
                },
            ];
        },
    },

    methods: {
        setIsDesctop() {
            this.isDesctop = document.body.clientWidth > 768;
        },
    },
    mounted() {
        window.addEventListener("resize", this.setIsDesctop);
    },
};
</script>
<style lang="scss">
.wrapperTwo {
    background-color: #4120c5;
    padding-bottom: 50rem;
    @media (max-width: 425px) {
        padding-bottom: 30rem;
    }
}
.pageTwoH3 {
    padding-top: 50rem;
    padding-left: 40rem;
    margin-bottom: 20rem;
    color: rgba(255, 255, 255, 0.6);
    font-weight: 500;
    font-size: 20rem;
    line-height: 28rem;
    @media (max-width: 425px) {
        margin-bottom: 40rem;

        padding-left: 20rem;
        padding-top: 30rem;
        font-size: 10rem;
        line-height: 12rem;
    }
}
.tenders {
    margin-top: 104rem;
    @media (max-width: 425px) {
        margin-top: 70rem;
    }
    a {
        cursor: pointer;
        margin-left: 40rem;

        font-size: 20rem;
        line-height: 28rem;
        text-decoration: underline;
        text-underline-offset: 5rem;
        color: rgba(255, 255, 255, 0.6);
        @media (max-width: 425px) {
            font-size: 10rem;
            line-height: 12rem;
            margin-left: 20rem;
        }
    }
}
</style>
