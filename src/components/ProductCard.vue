<script>
import { toHandlers } from 'vue';

export default {
    name: "ProductCard",
    props: {
        title: String,
        imgSrc: String,
        type: String
    },
    computed: {
        cardClass() {
            if (this.type === "lunga") {
                return "long"
            } else if (this.type === "corta") {
                return "short";
            } else {
                return "shortest";
            }
        }
    },
    methods: {
        // getClassName() {
        //     if (this.type === "lunga") {
        //         return "long"
        //     } else if (this.type === "corta") {
        //         return "short";
        //     } else {
        //         return "shortest";
        //     }
        // }
    }
}
</script>

<template>
    <div class="card" :class="cardClass">
        <img :src="imgSrc" :alt="title">
        <h4>{{ title }}</h4>
    </div>
</template>

<style lang="scss" scoped>
.card {
    background-color: white;
    width: calc(100% / 4 - 10px);
    margin: 5px;

    h4 {
        text-align: center;
        padding: .5rem;
    }

    &.long {
        border: 1px solid red;
    }

    &.short {
        border: 1px solid green;
    }

    &.shortest {
        border: 1px solid blue;
    }
}
</style>