<template>
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
.items {
    padding: 35rem 0 45rem 40rem;
    @media (max-width: 425px) {
        padding: 0rem 0 20rem 20rem;
    }
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
            width: 58rem;
            height: 58rem;
            position: absolute;
            right: 50rem;
            top: 50%;
            transform: translate(0, -50%);
            @media (max-width: 425px) {
                width: 40rem;
                height: 40rem;
                right: 20rem;
            }
        }

        @media (max-width: 425px) {
            font-size: 35rem;
            line-height: 40rem;
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
                @media (max-width: 425px) {
                    width: 40rem;
                    height: 40rem;
                }
            }
        }
    }

    p {
        margin-top: 45rem;
        width: 73%;
        font-size: 20rem;
        line-height: 140%;
        color: #fff;
        @media (max-width: 425px) {
            margin-top: 20rem;
            font-size: 14rem;
            width: 100%;
            padding-right: 20rem;
        }
    }
}
</style>
