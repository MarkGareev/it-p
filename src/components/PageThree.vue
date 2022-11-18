<template>
    <div>
        <div class="string">
            <h3 style="margin-left: 40px; margin-bottom: 20px">
                Услуги компании
            </h3>

            <div class="services">
                <a target="_blank" href="../1.pdf">
                    <u>Все услуги компании</u> <br />
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
.string {
    display: flex;
    justify-content: space-between;
    padding-right: 50px;
}
.services {
    font-size: 20px;
    line-height: 28px;
    text-align: right;
    text-underline-offset: 5px;

    a {
        text-decoration: none;
        color: #808080;
    }
}
.services-count {
    font-weight: 500;
    font-size: 80px;
    line-height: 85px;
    letter-spacing: -0.02em;
    color: #000000;
    margin-left: 40px;
    margin-bottom: 20px;
}

.services-item {
    position: relative;
    font-weight: 500;
    font-size: 20px;
    line-height: 28px;
    padding: 30px 0 0 0px;
    &:after {
        transform: translateX(-50%);
        left: 50%;
        content: "";
        height: 1px;
        width: calc(100% - 80px);
        position: absolute;
        top: 0;
        background-color: transparent;
    }
    &:not(&:first-child) {
        &:after {
            background-color: #000000;
        }
    }

    &-text {
        padding: 0px 40px 30px 40px;
    }

    a {
        cursor: default;
        text-decoration: none;
        color: #000000;
    }
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
.list-all {
    padding: 0;
    margin: 50px 0 50px 40px;
    font-size: 20px;
    line-height: 28px;

    cursor: pointer;
    background: none;
    border: none;
    text-decoration: underline;
    text-underline-offset: 5px;

    color: #808080;
}
</style>
