<template>
    <aside>
        <div class="headerNav">
            <div class="logo">
                <img src="@/assets/Logo.svg" alt="logo" />
            </div>
            <a href="tel:+7 342 204–59–68"><img src="../assets/phone.svg" alt="phone"></a>  
        </div>
        <div class="content">            
            <h2>
                Информационные технологии <br />
                — Поволжье
            </h2>

            <nav class="menu">
                <div
                    v-for="(item, index) in getListLinks"
                    :key="index"
                    class="menu-item"
                >
                    <button @click="goToPage(item.links)">
                        {{ item.title }}
                    </button>
                </div>
            </nav>
            <div class="listorg">
                <a
                    href="https://www.list-org.com/company/8001397"
                    target="_blank"
                    >Карточка компании на&nbsplist&#8209org
                </a>
            </div>
        </div>
        <div class="contacts">
            <div class="address">
                <a
                    target="_blank"
                    href="https://yandex.ru/maps/50/perm/house/chernushinskaya_ulitsa_22/YU8YdA5oTUIOQFttfXV5d3tiZg==/?ll=56.298479%2C57.986712&z=17.15"
                    >г. Пермь <br />
                    ул. Чернушинская, д. 22</a
                >
            </div>
            <button class="contact" href="tel:+7 342 204–59–68">
                +7 342 204–59–68
            </button>
        </div>
    </aside>
</template>

<script>
export default {
    name: "Navbar",
    methods: {
        goToPage(links) {
            this.$emit("goToPage", links);
        },
    },
    computed: {
        getListLinks() {
            return [
                {
                    title: "Компания",
                    links: "page-two",
                },
                {
                    title: "Услуги компании",
                    links: "page-three",
                },
                {
                    title: "Контакты",
                    links: "footer",
                },
            ];
        },
    },
};
</script>

<style lang="scss">


aside {
    top: 0;
    background-color: #23116b;
    height: 100vh;
    position: sticky;
    display: flex;
    flex-direction: column;
    @media (max-width: 768px) {
        z-index: 3;
        height: 100rem;
    }
    @media (max-width: 425px) {
        height: 60rem;
    }
    .headerNav {
        a {
            display: none;
        }
        @media (max-width: 768px) {
            display: flex;
            justify-content: space-between;
            padding: 20rem 40rem;
            align-items: center;
            a {
                display: block;
                padding: 0;
                border: none;
                background-color: transparent;
                img {
                    margin-right: 7rem;
                    width: 60rem;
                    height: 60rem;
                }
            }
        }
        @media (max-width: 425px) {
            padding: 0 20rem;
            height: 100%;
            a {
                height: 40rem;
                width: 40rem;
                img {
                    width: 40rem;
                    height: 40rem;
                }
            }
        }
    }
    .logo {
        padding: 50rem 40rem 20rem 40rem;
            img {
                width: 236rem;
                max-width: 236px;
            }
            @media (max-width: 768px) {
                padding: 0;
                img {
                    @media (max-width: 425px) {
                        height: 30rem;
                        width: 185rem;
                    }
                }
            }
        }
    .content {
        flex: 1 0 auto;
        @media (max-width: 768px) {
            display: none;

        }
        h2 {
            font-weight: 500;
            font-size: 12rem;
            line-height: 150%;
            color: rgba(255, 255, 255, 0.6);
            margin-bottom: 80rem;
            padding-left: 40rem;
        }
        .menu-item {
            button {
                display: flex;
                align-items: center;
                justify-content: center;
                color: #fff;
                background: none;
                cursor: pointer;
                justify-content: flex-start;
                padding: 25rem 0 25rem 40rem;
                width: 100%;
                border: none;
                border-bottom: 2rem solid rgba(255, 255, 255, 0.2);
                font-weight: 500;
                font-size: 20rem;
                line-height: 28rem;
            }
            &:last-child {
                button {
                    border-bottom: none;
                }
            }
        }
        .listorg {
            margin: 25rem 40rem;
            a {
                font-size: 20rem;
                line-height: 140%;
                text-underline-offset: 5rem;
                text-decoration-line: underline;
                color: rgba(255, 255, 255, 0.5);
            }
        }
    }
    .contacts {
        flex: 0 0 auto;
        margin-bottom: 50rem;
        @media (max-width: 768px) {
            display: none;
        }
        .address {
            margin-left: 40rem;
            margin-bottom: 50rem;
            font-size: 20rem;
            line-height: 140%;
            a {
                color: #fff;
                text-decoration: none;
            }
        }
        .contact {
            cursor: pointer;
            margin-left: 40rem;
            padding: 28rem 0;
            width: calc(100% - 80rem);
            height: 80rem;
            background-color: transparent;
            border: 2rem solid rgba(255, 255, 255, 0.2);

            font-weight: 500;
            font-size: 20rem;
            line-height: 24rem;

            color: #ffffff;
        }
    }
    
}
</style>
