<template>
    <footer>
        <h3>Закажите звонок</h3>

        <form>
            <input type="hidden" name="project_name" value="IT-P" />
            <input
                type="hidden"
                name="admin_email"
                value="Mbond@rescom-vt.ru"
            />
            <input type="hidden" name="form_subject" value="Заявка на звонок" />

            <input type="text" name="Имя" placeholder="Имя" />
            <input type="text" name="Email" placeholder="Email" />
            <input
                class="full"
                type="tel"
                name="Телефон"
                placeholder="Номер телефона"
            />
            <button class="call full">Заказать звонок</button>
        </form>
        <div class="footer-contacts">
            <img
                class="footer-contacts-logo"
                src="../assets/LogoFooter.svg"
                alt="Logo"
            />

            <div class="footer-contacts-location">
                <div class="footer-contacts-location-address">
                    г. Пермь <br />
                    ул. Чернушинская, д. 22
                </div>
                <a
                    target="_blank"
                    href="https://yandex.ru/maps/50/perm/house/chernushinskaya_ulitsa_22/YU8YdA5oTUIOQFttfXV5d3tiZg==/?ll=56.298479%2C57.986712&z=17.15"
                    class="footer-contacts-location-onmap"
                    >Смотреть на карте</a
                >
            </div>
        </div>
    </footer>
</template>
<script>
export default {
    name: "Footer",
};
</script>
<style lang="scss">
footer {
    position: relative;
    height: 800rem;
    padding: 50rem 40rem 40rem 40rem;
    background: #000000;
    @media (max-width: 425px) {
        padding: 30rem 20rem;
        height: 550rem;
    }
}
form {
    display: grid;
    grid-template-rows: repeat(3, max-content);
    margin-top: 30rem;
    gap: 20rem;

    grid-template-columns: repeat(2, 1fr);
    @media (max-width: 768px) {
        grid-template-rows: repeat(4, max-content);
        grid-template-columns: 1fr;
    }
    .full {
        grid-column: 1/3;
        @media (max-width: 768px) {
            grid-column: 1/2;
        }
    }
}
input {
    font-weight: 500;
    font-size: 20rem;
    line-height: 28rem;
    color: #808080;
    padding-left: 30rem;
    height: 80rem;
    border: 1rem solid #ffffff;
    background-color: #000000;
    @media (max-width: 425px) {
        font-size: 14rem;
        line-height: 17rem;
        height: 60rem;
    }
    &:enabled {
        color: #fff;
    }
    &:focus {
        outline: 0 !important;
    }
}
.call {
    min-height: 80rem;
    cursor: pointer;
    background-color: #4120c5;
    border: none;
    color: #fff;
    font-weight: 500;
    font-size: 20rem;
    line-height: 24rem;

    @media (max-width: 425px) {
        font-size: 14rem;
        line-height: 17rem;
        min-height: 60rem;
    }
}
.footer-contacts {
    position: absolute;
    bottom: 50rem;
    width: calc(100% - 40rem);
    display: grid;
    gap: 30rem;
    grid-template-columns: 1fr 1fr;
    justify-items: end;
    align-items: end;
    @media (max-width: 425px) {
        grid-template-columns: unset;
        grid-template-rows: 1fr 1fr;
        justify-items: start;
        bottom: 30rem;
    }
    &-logo {
        justify-self: start;
        width: 100%;
        max-width: 720px;
        @media (max-width: 425px) {
            grid-row-start: 2;
        }
    }
    &-location {
        margin-right: 50rem;
        @media (max-width: 425px) {
            margin-right: 0;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            width: 100%;
        }
        &-address {
            font-size: 20rem;
            line-height: 28rem;
            color: #ffffff;
            margin-bottom: 30rem;
            @media (max-width: 425px) {
                margin-bottom: 0rem;
                font-size: 10rem;
                line-height: 12rem;
            }
        }
        &-onmap {
            cursor: pointer;
            font-size: 20rem;
            line-height: 28rem;
            text-decoration: underline;
            text-underline-offset: 5rem;
            color: #808080;
            @media (max-width: 425px) {
                font-size: 10rem;
                line-height: 12rem;
                align-self: end;
                justify-self: end;
            }
        }
    }
}
</style>
