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
                <h1 @click="setActiveIndex(index)">{{ item.title }}</h1>
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
    padding-left: 40px;
    margin-bottom: 20px;
    color: rgba(255, 255, 255, 0.6);
    font-weight: 500;
    font-size: 20px;
    line-height: 28px;
}
.items {
    padding: 35px 0px 45px 40px;
    color: #fff;

    h1 {
        cursor: pointer;
        position: relative;

        font-weight: 500;
        font-size: 80px;
        line-height: 85px;
        letter-spacing: -0.02em;
        color: #fff;
        &::after {
            width: 58px;
            height: 58px;
            content: url(../assets/EllipseIcon.svg);
            position: absolute;
            right: 51px;
            margin: 0;
        }
    }
    &:not(:last-child) {
        border-bottom: 2px solid #ffffff;
    }
    &.active {
        h1 {
            &::after {
                content: url(../assets/EllipseIcon180.svg);
            }
        }
    }

    p {
        margin-top: 45px;
        width: 1043px;
        font-size: 20px;
        line-height: 140%;
        color: #fff;
    }
}
</style>
