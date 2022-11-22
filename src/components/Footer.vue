<template>
    <div>
        <footer>
            <h3>Закажите звонок</h3>

            <form>
                <input type="hidden" name="project_name" value="IT-P" />
                <input
                    type="hidden"
                    name="admin_email"
                    value="Mbond@rescom-vt.ru"
                />
                <input
                    type="hidden"
                    name="form_subject"
                    value="Заявка на звонок"
                />

                <input class="half" type="text" name="Имя" placeholder="Имя" />
                <input
                    class="half"
                    type="tel"
                    name="Email"
                    placeholder="Email"
                />
                <input
                    class="full"
                    type="text"
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
                        ул. Куйбышева, д. 47
                    </div>
                    <a
                        target="_blank"
                        href="https://yandex.ru/maps/50/perm/house/ulitsa_kuybysheva_47/YU8YdARnTk0OQFtifXxxcnxiYg==/?ll=56.237789%2C58.003016&z=17"
                        class="footer-contacts-location-onmap"
                        >Смотреть на карте</a
                    >
                </div>
            </div>
        </footer>
    </div>
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
}
form {
    display: grid;
    grid-template-rows: repeat(3, max-content);
    margin-top: 30rem;
    gap: 20rem;

    grid-template-columns: repeat(2, 1fr);
    .full {
        grid-column: 1/3;
    }
}
input {
    font-weight: 500;
    font-size: 20rem;
    line-height: 28rem;
    color: #808080;
    padding-left: 30rem;
    &:enabled {
        color: #fff;
    }
    &:focus {
        outline: 0 !important;
    }
    height: 80rem;
    border: 1rem solid #ffffff;
    background-color: #000000;
}
.call {
    min-height: 80rem;
    height: 100%;
    cursor: pointer;
    background-color: #4120c5;
    color: #fff;
    font-weight: 500;
    font-size: 20rem;
    line-height: 24rem;
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

    &-logo {
        justify-self: start;
        width: 100%;
        max-width: 720px;
    }
    &-location {
        margin-right: 50rem;

        &-address {
            font-size: 20rem;
            line-height: 28rem;
            color: #ffffff;
            margin-bottom: 30rem;
        }
        &-onmap {
            cursor: pointer;
            font-size: 20rem;
            line-height: 28rem;
            text-decoration: underline;
            text-underline-offset: 5rem;
            color: #808080;
        }
    }
}
</style>
