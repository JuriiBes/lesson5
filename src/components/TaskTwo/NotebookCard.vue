<template>
    <div class="notebook__card">
        <a :href="notebookCardData.link" class="notebook__image-body">
            <img :src="notebookCardData.imgSrc" class="notebook__image" alt="image notebook" />
        </a>

        <div class="notebook__right-side">
            <a :href="notebookCardData.link" class="notebook__title">{{ notebookCardData.title }}</a>
            <div class="notebook__discount">
                <template v-if="auditDiscount">
                    <div class="notebook__price-difference">
                        Ваша економія: <span>{{ notebookCardData.discount }} ₴</span>
                    </div>
                    <div class="notebook__old-price">
                        <span>{{ notebookCardData.oldPrice }}</span> ₴
                    </div>
                </template>
            </div>
            <div class="notebook__price-block">
                <div class="notebook__price">
                    <span>{{ notebookCardData.price }}</span> ₴
                </div>
                <button class="notebook__button">Купити</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NotebookCard',
    props: {
        notebookCardData: {
            type: Object,
            default: () => ({}),
        },
    },
    computed: {
        auditDiscount() {
            return this.notebookCardData.discount && this.notebookCardData.oldPrice
        },
    },
}
</script>

<style lang="scss" scoped>
.notebook {
    // .notebook__card
    &__card {
        display: flex;
        flex-direction: row;
        column-gap: 10px;
        align-items: center;
        width: 500px;
        padding: 5px 10px 15px;

        &:not(:last-child) {
            border-bottom: 2px solid grey;
        }
    }
    // .notebook__imag-body
    &__image-body {
        flex: 1 0 30%;
        position: relative;
        overflow: hidden;
        object-fit: cover;
        padding-top: 30%;
        &:hover {
            .notebook__image {
                transform: scale(1.02);
            }
        }
    }
    // .notebook__image
    &__image {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        transition: 0.3s;
    }
    // .notebook__right-side
    &__right-side {
        flex: 1 1 auto;
        display: flex;
        flex-direction: column;
        row-gap: 10px;
        justify-content: flex-start;
    }
    // .notebook__title
    &__title {
        font-size: 22px;
        color: blue;
        text-decoration: none;
        transition: color ease 0.3s;
        &:hover {
            color: blueviolet;
        }
    }
    // .notebook__discount
    &__discount {
        font-size: 14px;
        display: flex;
        flex-direction: column;
        row-gap: 15px;
        color: grey;
    }
    // .notebook__price-difference
    &__price-difference {
        & span {
            color: red;
        }
    }
    // .notebook__old-price
    &__old-price {
        color: grey;
        font-size: 18px;
        span {
            font-size: 22px;
            text-decoration: line-through;
        }
    }
    // .notebook__price-block
    &__price-block {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    // .notebook__price
    &__price {
        font-size: 30px;
        color: red;
    }
    // .notebook__button
    &__button {
        padding: 5px 15px;
        font-size: 18px;
        color: azure;
        border-radius: 4px;
        background-color: #38a54a;
        transition: background-color ease 0.3s;
        &:hover {
            background-color: #277133;
        }
    }
}
</style>
