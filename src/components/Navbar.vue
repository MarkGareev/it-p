<template>
    <aside>
        <div class="logo">
                <a href="#"><img src="@/assets/Logo.svg" alt="logo" /></a>
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
                    href="https://yandex.ru/maps/50/perm/house/ulitsa_kuybysheva_47/YU8YdARnTk0OQFtifXxxcnxiYg==/?indoorLevel=1-2&ll=56.237789%2C58.003016&z=17"
                    >г. Пермь <br />
                    ул. Куйбышева, д. 47</a
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
    .logo {
            a {
                img {
                    width: 236rem;
                    max-width: 236px;
                }
            }
            padding: 50rem 40rem 20rem 40rem;
        }
    top: 0;
    background-color: #23116b;

    height: 100vh;
    position: sticky;
    display: flex;
    flex-direction: column;

    .content {
        flex: 1 0 auto;
        
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
