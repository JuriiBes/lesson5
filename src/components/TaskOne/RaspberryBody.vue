<template>
    <div class="body__shops">
        <raspberry-card-item v-for="product in raspberryLinksCard" :key="product.id" :raspberry-items="product" />
    </div>
</template>

<script>
import RaspberryCardItem from './RaspberryCardItem.vue'
export default {
    name: 'RaspberryBody',
    components: {
        RaspberryCardItem,
    },
    props: {
        raspberryLinksCard: {
            type: Array,
            default: () => [],
        },
    },
}
</script>

<style lang="scss" scoped>
.body {
    // .body__shops
    &__shops {
        display: flex;
        flex-wrap: wrap;
        gap: 15px;
        align-items: center;
        justify-content: center;
    }
}
</style>
