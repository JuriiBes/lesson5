<template>
    <div class="raspberry__body">
        <raspberry-body :raspberry-links-card="raspberryList" />
    </div>
</template>

<script>
import { raspberryList } from '@/constants/raspberry_list.js'
import RaspberryBody from './RaspberryBody.vue'
export default {
    name: 'TaskOne',
    components: {
        RaspberryBody,
    },
    data() {
        return {
            raspberryList,
        }
    },
}
</script>

<style lang="scss" scoped>
.raspberry {
    // .raspberry__body
    &__body {
        padding: 15px 25px;
        background-color: #262b0b;
        margin-bottom: 25px;
    }
}
</style>
