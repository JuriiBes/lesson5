<template>
    <div class="product__card">
        <div class="product__img-body">
            <img :src="raspberryItems.imgSrc" alt="" class="product__img" />
        </div>
        <div class="product__shop-name shop">
            <div class="shop__logo"><img :src="raspberryItems.logo" alt="" /></div>
            <div class="shop__name">{{ raspberryItems.companyTitle }}</div>
            <div v-if="auditBalancedInStock" class="shop__balanced">
                <div>
                    <div class="shop__balanced-true">В наявності</div>
                </div>
            </div>
        </div>
        <div class="product__description">{{ raspberryItems.description }}</div>
    </div>
</template>

<script>
export default {
    name: 'RaspberryCardItem',
    props: {
        raspberryItems: {
            type: Object,
            default: () => ({}),
        },
    },
    computed: {
        auditBalancedInStock() {
            return this.raspberryItems.balanceInStock > 0
        },
    },
}
</script>

<style lang="scss" scoped>
.product {
    // .product__card
    &__card {
        display: flex;
        flex-direction: column;
        row-gap: 10px;
        max-width: 250px;
        padding: 10px;
        background-color: rgba(250, 235, 215, 0.4);
        border-radius: 15px;
        cursor: pointer;
    }
    &__card:hover {
        & .product__img {
            transform: scale(1.03);
        }
    }
    // .product__img-body
    &__img-body {
        position: relative;
        width: 250px;
        padding-top: 90%;
        overflow: hidden;
        object-fit: cover;
        border-radius: 15px;
    }
    // .product__img
    &__img {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        transition: 0.3s;
    }
    // .product__description
    &__description {
        font-size: 22px;
        line-height: 0.7;
        color: white;
    }
}
.shop {
    display: flex;
    column-gap: 10px;
    align-items: flex-end;

    // .shop__logo
    &__logo {
        max-width: 20px;
    }
    // .shop__name
    &__name {
        font-size: 16px;
        color: white;
    }
    // .shop__balanced
    &__balanced {
        display: flex;
        column-gap: 10px;
        color: rgb(7, 205, 7);
        font-size: 14px;
    }
    &__balanced::before {
        content: '';
        display: block;
        width: 4px;
        height: 4px;
        border-radius: 50%;
        background-color: aliceblue;
        margin-top: 6px;
    }
    // .shop__balanced-true
    &__balanced-true {
    }
}
</style>
