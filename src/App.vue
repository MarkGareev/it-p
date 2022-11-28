<template>
    <div id="app" class="app">
        <Navbar class="navbar" @goToPage="goToPage1" />
        <div class="main" v-on:scroll="onScroll">
            <PageOne />
            <PageTwo id="page-two" />
            <PageThree id="page-three" />
            <Footer id="footer" />
            <button class="upArrow" v-if="getIsShowButton" @click="scrollTop">
                <img src="../src/assets/up.svg" alt="" />
            </button>
        </div>
    </div>
</template>

<script>
import Navbar from "./components/Navbar";
import PageOne from "./components/PageOne";
import PageTwo from "./components/PageTwo";
import PageThree from "./components/PageThree";
import Footer from "./components/Footer";

export default {
    data() {
        return {
            positionScroll: 0,
        };
    },
    name: "App",
    created() {
        window.addEventListener("scroll", this.onScroll);
    },
    destroyed() {
        window.removeEventListener("scroll", this.onScroll);
    },
    methods: {
        scrollTop() {
            const elem = document.body;
            elem.scrollIntoView({
                behavior: "smooth",
            });
        },
        onScroll(event) {
            this.positionScroll = event.target.scrollingElement.scrollTop;
        },
        goToPage1(links) {
            const element = document.querySelector(`#${links}`);
            element.scrollIntoView({
                behavior: "smooth",
            });
        },
    },

    computed: {
        getIsShowButton() {
            return this.positionScroll > 0;
        },
    },
    components: { Navbar, PageOne, PageTwo, PageThree, Footer },
};
</script>

<style lang="scss">
* {
    font-family: "Grtsk Peta";
    box-sizing: border-box;
    margin: 0px;
    padding: 0px;
}
html {
    font-size: 1px;
}

.app {
    max-width: 100%;
    display: grid;
    grid-template-columns: 1fr 3fr;
}

.upArrow {
    cursor: pointer;
    background-color: #eff0f5;
    border: 1rem solid#EFF0F5;
    border-radius: 50%;
    position: fixed;
    width: 80rem;
    height: 80rem;

    right: 40rem;
    bottom: 80rem;
    img {
        z-index: 2;
        width: 20%;
        content: url(assets/up.svg);
    }
}
@media (max-width: 1580px) {
    html {
        font-size: 0.9px;
    }
}
@media (max-width: 1255px) {
    html {
        font-size: 0.7px;
    }
}
@media (max-width: 1000px) {
    html {
        font-size: 0.6px;
    }
}
@media (max-width: 768px) {
    .app {
        display: flex !important;
        flex-direction: column;
    }
    .upArrow {
        display: none;
    }
}
@media (max-width: 550px) {
    html {
        font-size: 0.45px;
    }
}
@media (max-width: 425px) {
    html {
        font-size: 1px;
    }
}

@media (max-width: 385px) {
    html {
        font-size: 0.9px;
    }
}
@media (max-width: 350px) {
    html {
        font-size: 0.8px;
    }
}
@media (max-width: 310px) {
    html {
        font-size: 0.7px;
    }
}
@font-face {
    font-family: "Grtsk Peta";
    src: local("Grtsk Peta Medium"), local("Grtsk-Peta-Medium"),
        url("./assets/GrtskPeta-Medium.woff2") format("woff2"),
        url("./assets/GrtskPeta-Medium.woff") format("woff"),
        url("./assets/GrtskPeta-Medium.ttf") format("truetype");
    font-weight: 500;
    font-style: normal;
}
</style>
