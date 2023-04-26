<template>
    <div class="j-card col-6">
        <img :src="item.img" :alt="item.text">

        <div class="j-content">
            <div class="upcoming">
                <h3 class="m-0">{{ item.genre }}</h3>
            </div>

            <h3 class="m-0 text-white">{{ item.text }}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name: 'JumboCard',
    props: [
        'item'
    ]
}
</script>

<style lang="scss" scoped>
.j-card {
    position: relative;

    img {
        width: 100%;
        display: block;
        height: 100%;
    }

    .j-content {
        position: absolute;
        top: 35%;
        left: 55%;
    }
}
</style>