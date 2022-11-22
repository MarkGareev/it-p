<template>
    <div>
        <h3 class="pageTwoH3">Компания</h3>
        <div>
            <div
                class="items"
                v-for="(item, index) in list"
                :key="index"
                :class="{ active: listActiveIndex.includes(index) }"
            >
                <h1 @click="setActiveIndex(index)">
                    {{ item.title }}
                    <img src="../assets/EllipseIcon.svg" alt="EllipseIcon" />
                </h1>
                <p v-if="listActiveIndex.includes(index)">{{ item.text }}</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "listItem",
    data() {
        return {
            listActiveIndex: [],
        };
    },
    props: {
        list: {
            type: Array,
            requared: true,
        },
    },
    methods: {
        setActiveIndex(index) {
            if (this.listActiveIndex.includes(index)) {
                const currentIndex = this.listActiveIndex.indexOf(index);
                this.listActiveIndex.splice(currentIndex, 1);
            } else {
                this.listActiveIndex.push(index);
            }
        },
    },
};
</script>

<style lang="scss">
.pageTwoH3 {
    padding-left: 40rem;
    margin-bottom: 20rem;
    color: rgba(255, 255, 255, 0.6);
    font-weight: 500;
    font-size: 20rem;
    line-height: 28rem;
}
.items {
    padding: 35rem 0 45rem 40rem;

    color: #fff;

    h1 {
        cursor: pointer;
        position: relative;
        padding-right: 150rem;
        font-weight: 500;
        font-size: 80rem;
        line-height: 85rem;
        letter-spacing: -0.02em;
        color: #fff;
        img {
            // content: url(../assets/EllipseIcon.svg);
            width: 58rem;
            height: 58rem;
            position: absolute;
            right: 51rem;
            top: 50%;
            transform: translate(0, -50%);
        }
    }
    &:not(:last-child) {
        border-bottom: 2rem solid #ffffff;
    }
    &.active {
        h1 {
            img {
                content: url(../assets/EllipseIcon180.svg);
                width: 58rem;
                height: 58rem;
            }
        }
    }

    p {
        margin-top: 45rem;
        width: 73%;
        font-size: 20rem;
        line-height: 140%;
        color: #fff;
    }
}
</style>
