<template>
    <div class="j-card col-6">
        <img :src="item.img" :alt="item.text">

        <div class="j-content">
            <div class="upcoming">
                <h4 class="m-0">{{ item.genre }}</h4>
            </div>

            <h4 class="m-0 text-white">{{ item.text }}</h4>
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

    &:hover {
        scale: 1.1;
        z-index: 999;
        transition: 1s;
    }

    img {
        width: 100%;
        display: block;
        height: 100%;
    }

    .j-content {
        position: absolute;
        top: 35%;
        left: 50%;
        width: 250px;
    }
}
</style>