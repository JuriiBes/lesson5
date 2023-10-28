<template>
    <div class="card__favorite-body">
        <favorite-link v-for="card in cardListData" :key="card.id" :card-date="card" />
    </div>
</template>

<script>
import FavoriteLink from '@/components/FavoriteLink.vue'
export default {
    name: 'FavoriteBody',
    components: {
        FavoriteLink,
    },
    props: {
        cardListData: {
            type: Array,
            default: () => [],
        },
    },
}
</script>

<style lang="scss" scoped>
.card {
    // .card__favorite-body
    &__favorite-body {
        display: flex;
        flex-wrap: wrap;
        gap: 25px;
        padding: 50px;
        background-color: #3b1a1a;
        justify-content: center;
        margin-bottom: 25px;
    }
}
</style>
