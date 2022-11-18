<template>
    <aside>
        <div class="content">
            <div class="logo">
                <a href="#"><img src="@/assets/Logo.svg" alt="logo" /></a>
            </div>
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
                    >Карточка компании на list-org</a
                >
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
    top: 0px;
    background-color: #23116b;

    height: 100vh;
    position: sticky;
    display: flex;
    flex-direction: column;

    .content {
        flex: 1 0 auto;
        .logo {
            padding: 50px 0px 20px 40px;
        }
        h2 {
            font-weight: 500;
            font-size: 12px;
            line-height: 18px;
            color: rgba(255, 255, 255, 0.6);
            margin-bottom: 80px;
            padding-left: 40px;
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
                padding: 25px 0 25px 40px;
                width: 100%;
                border: none;
                border-bottom: 2px solid rgba(255, 255, 255, 0.2);
                font-weight: 500;
                font-size: 20px;
                line-height: 28px;
            }
            &:last-child {
                button {
                    border-bottom: none;
                }
            }
        }

        .listorg {
            padding-right: 40px;
            margin-top: 25px;
            padding-left: 40px;
            font-size: 20px;
            line-height: 28px;
            a {
                text-underline-offset: 5px;

                text-decoration-line: underline;
                color: rgba(255, 255, 255, 0.5);
            }
        }
    }

    .contacts {
        flex: 0 0 auto;

        margin-bottom: 50px;

        .address {
            margin-left: 40px;
            margin-bottom: 50px;
            font-size: 20px;
            line-height: 28px;
            a {
                color: #fff;
                text-decoration: none;
            }
        }
        .contact {
            cursor: pointer;
            margin-left: 40px;
            // margin-right: 40px;
            padding: 28px 0;
            width: calc(100% - 80px);
            // padding: 28px 0;
            background-color: transparent;
            border: 2px solid rgba(255, 255, 255, 0.2);

            font-weight: 500;
            font-size: 20px;
            line-height: 24px;

            color: #ffffff;
        }
    }
}
</style>
