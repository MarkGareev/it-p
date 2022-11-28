<template>
    <div class="wrapperThree">
        <div class="string">
            <h3>Услуги компании</h3>

            <div class="services">
                <a target="_blank" href="../1.pdf">
                    <u>Все услуги</u> <br />
                    (PDF)
                </a>
            </div>
        </div>
        <div class="services-count">
            <span>{{ getListServices.length }}</span>
        </div>
        <div class="services-list">
            <div
                v-for="(item, index) in getNewListServices"
                :key="index"
                class="services-item"
            >
                <div class="services-item-text">
                    <a>{{ item.title }} </a>
                </div>
            </div>
        </div>
        <button v-if="show" class="list-all" @click="showFullList">
            Смотреть полный список
        </button>
        <button v-if="!show" class="list-all" @click="showFullList">
            Скрыть полный список
        </button>
    </div>
</template>
<script>
export default {
    name: "PageThree",
    data() {
        return {
            listCount: 5,
            show: true,
        };
    },
    computed: {
        getListServices() {
            return [
                {
                    title: "Разработка прикладного ПО для АСУТП",
                    links: "#",
                },
                {
                    title: "Разработка ПО систем удалённого мониторинга и диагностики технологического оборудования",
                    links: "#",
                },
                {
                    title: "Разработка низкоуровневых программ сетевой передачи данных по технологическим протоколам",
                    links: "#",
                },
                {
                    title: "Поставка ПО российских и зарубежных производителей",
                    links: "#",
                },
                {
                    title: "Поставка компьютерного оборудования российских и зарубежных производителей",
                    links: "#",
                },
                {
                    title: "Поставка печатной и оргтехники российских и зарубежных производителей",
                    links: "#",
                },
                {
                    title: "Поставка серверного оборудования российских и зарубежных производителей",
                    links: "#",
                },
                {
                    title: "Разработка и внедрение проектов ЦОД",
                    links: "#",
                },
                {
                    title: "Системная интеграция",
                    links: "#",
                },
                {
                    title: "ИТ-консалтинг и сопровождение",
                    links: "#",
                },
                {
                    title: "Работа с гособоронзаказом",
                    links: "#",
                },
                {
                    title: "Параллельный импорт продукции ведущих зарубежных производителей",
                    links: "#",
                },
                {
                    title: "Разработка и внедрение систем ВКС на базе оборудования российских и зарубежных производителей",
                    links: "#",
                },
            ];
        },
        getNewListServices() {
            return this.getListServices.filter(
                (item, index) => index + 1 <= this.listCount
            );
        },
    },
    methods: {
        showFullList() {
            this.show = !this.show;
            this.show
                ? (this.listCount = 5)
                : (this.listCount = this.getListServices.length);
        },
    },
};
</script>
<style lang="scss">
.wrapperThree {
    padding: 50rem 0;
    @media (max-width: 425px) {
        padding: 30rem 0;
    }
}
.string {
    h3 {
        margin-left: 40rem;
        @media (max-width: 425px) {
            margin-left: 20rem;
            font-size: 10rem;
            line-height: 12rem;
        }
    }
    display: flex;
    justify-content: space-between;
    padding-right: 50rem;
    @media (max-width: 425px) {
        padding-right: 20rem;
    }
}
.services {
    font-size: 20rem;
    line-height: 28rem;
    text-align: right;
    text-underline-offset: 5rem;
    a {
        text-decoration: none;
        color: #808080;
    }
    @media (max-width: 425px) {
        font-size: 10rem;
        line-height: 15rem;
        text-underline-offset: 3rem;
    }
}
.services-count {
    font-weight: 500;
    font-size: 80rem;
    line-height: 85rem;
    letter-spacing: -0.02em;
    color: #000000;
    margin-left: 40rem;
    margin-bottom: 20rem;
    @media (max-width: 425px) {
        margin-top: -20rem;
        margin-left: 20rem;
        font-size: 40rem;
        margin-bottom: -10rem;
        padding: 0;
    }
}

.services-item {
    position: relative;
    font-weight: 500;
    font-size: 20rem;
    line-height: 28rem;
    padding-top: 30rem;

    @media (max-width: 425px) {
        padding-top: 10rem;
        font-size: 14rem;
        line-height: 20rem;
    }
    &:after {
        transform: translateX(-50%);
        left: 50%;
        content: "";
        height: 1rem;
        width: calc(100% - 80rem);
        position: absolute;
        top: 0;
        background-color: transparent;
        @media (max-width: 425px) {
            width: calc(100% - 40rem);
        }
    }
    &:not(&:first-child) {
        &:after {
            background-color: #000000;
        }
    }

    &-text {
        padding: 0rem 40rem 30rem 40rem;
        @media (max-width: 425px) {
            padding: 0rem 20rem 10rem 20rem;
        }
    }

    @media (min-width: 769px) {
        &:hover {
            background: #4120c5;

            &:not(&:first-child) {
                &:after {
                    background-color: transparent;
                }
            }

            + .services-item {
                &:after {
                    background-color: transparent;
                }
            }
            a {
                color: #fff;
            }
        }
    }
}
.list-all {
    padding: 0;
    margin: 50rem 0 0 40rem;
    font-size: 20rem;
    line-height: 140%;

    cursor: pointer;
    background: none;
    border: none;
    text-decoration: underline;
    text-underline-offset: 5rem;

    color: #808080;
    @media (max-width: 425px) {
        margin: 30rem 0 0 20rem;
        font-size: 10rem;
        line-height: 12rem;
    }
}
</style>
