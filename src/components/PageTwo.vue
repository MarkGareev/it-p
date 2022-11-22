<template>
    <div class="wrapperTwo">
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
        };
    },
    computed: {
        getList() {
            return [
                {
                    title: "История создания компании",
                    text: "Компания была создана в 2014 г. в Перми путём объединения ИТ-специалистов, имевших к этому времени широкий опыт работы на рынке Приволжского федерального округа. Нацеленность на сотрудничество с государственными и корпоративными заказчиками позволила ещё больше расширить собственные компетенции, добавила бесценного опыта  и обеспечила устойчивое развитие.",
                },
                {
                    title: "Государственные тендеры",
                    text: "Тесное сотрудничество со многими производителями высокотехнологичных решений дало возможность компании стать победителем в более или выступить, чем 100 государственных и коммерческих тендеров на общую сумму более 1 млрд. руб.",
                },
                {
                    title: "Преимущества",
                    text: "Компетентность и ответственность - основные преимущества нашей компании.",
                },
            ];
        },
    },
    props: {},
};
</script>
<style lang="scss">
.wrapperTwo {
    background-color: #4120c5;
    padding-bottom: 50rem;
}

.tenders {
    margin-top: 104rem;

    a {
        cursor: pointer;

        font-size: 20rem;
        line-height: 28rem;
        margin-left: 40rem;
        text-decoration: underline;
        text-underline-offset: 5rem;
        color: rgba(255, 255, 255, 0.6);
    }
}
</style>
