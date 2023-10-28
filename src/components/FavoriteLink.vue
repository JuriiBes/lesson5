<template>
    <div class="card">
        <a :href="cardDate.link" class="card__link" target="_blank">
            <div class="card__icon-body">
                <img :src="cardDate.imgSrc" alt="icon" class="card__icon" />
            </div>
            <div class="card__title">{{ cardDate.title }}</div>
        </a>
    </div>
</template>

<script>
export default {
    name: 'FavoriteLink',

    props: {
        // Прописуємо кожний параметр окремо
        // titleCard: {
        //     type: String,
        //     default: '',
        // },
        // iconCard: {
        //     type: String,
        //     default: '',
        // },
        // linkCard: {
        //     type: String,
        //     default: '',
        // },
        //  Отритмуємо об'єкт з данними
        cardDate: {
            type: Object,
            default: () => ({}),
        },
    },
}
</script>

<style lang="scss" scoped>
.card {
    // .card__link
    &__link {
        display: flex;
        width: 80px;
        align-items: center;
        flex-direction: column;
        row-gap: 15px;
        background-color: rgba(128, 128, 128, 0.05);
        text-decoration: none;
        cursor: pointer;
        padding: 25px 10px;
        border-radius: 15px;
        transition: background-color ease 0.3s;
    }
    &__link:hover {
        background-color: rgba(128, 128, 128, 0.15);
    }

    // .card__icon-body
    &__icon-body {
        position: relative;
        width: 50px;
        height: 50px;
        border-radius: 50%;
        background-color: rgb(38, 36, 36);
        overflow: hidden;
        object-fit: cover;
    }
    // .card__icon
    &__icon {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 80%;
        height: auto;
    }
    // .card__title
    &__title {
        text-align: center;
        font-size: 22px;
        color: rgb(244, 239, 239);
    }
}
</style>
