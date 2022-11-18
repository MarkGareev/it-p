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
                <img src="../assets/LogoFooter.svg" alt="Logo" />

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
    height: 800px;
    padding: 50px 40px 40px 40px;
    background: #000000;
}
form {
    grid-template-rows: repeat(3, max-content);
    margin-top: 30px;
    display: grid;
    gap: 20px;

    grid-template-columns: repeat(2, 1fr);
    .full {
        grid-column: 1/3;
    }
}
input {
    font-weight: 500;
    font-size: 20px;
    line-height: 28px;
    color: #808080;
    padding-left: 30px;
    &:enabled {
        color: #fff;
    }
    &:focus {
        outline: 0 !important;
    }
    height: 80px;
    border: 1px solid #ffffff;
    background-color: #000000;
}
.call {
    min-height: 80px;
    height: 100%;
    cursor: pointer;
    background-color: #4120c5;
    color: #fff;
    font-weight: 500;
    font-size: 20px;
    line-height: 24px;
}
.footer-contacts {
    position: absolute;
    bottom: 50px;
    display: flex;
    align-items: flex-start;
    &-location {
        display: grid;
        margin-left: 159px;
        gap: 30px;
        &-address {
            font-size: 20px;
            line-height: 28px;
            color: #ffffff;
        }
        &-onmap {
            cursor: pointer;

            font-size: 20px;
            line-height: 28px;
            text-decoration: underline;
            text-underline-offset: 5px;
            color: #808080;
        }
    }
}
</style>
