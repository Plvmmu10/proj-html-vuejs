<template>
    <div class="col-4" v-for="item in specialContent">
        <div class="card">
            <!-- Card image -->
            <div class="card-image">
                <img :src="item.img" :alt="item.name" class="w-100 h-100">
            </div>

            <!-- Card Body -->
            <div class="card-body">
                <h6 class="m-0 text-white">{{ item.name }}</h6>
                <a href="#">Shop Now</a>
            </div>

            <button>{{ item.name }}</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SpecialComponent',
    data() {
        return {
            specialContent: [
                {
                    img: 'img/category-image-02-446x550_t.jpg',
                    name: 'Battlefield'
                },
                {
                    img: 'img/category-image-01-446x550_t.jpg',
                    name: 'P.U.B.G'
                },
                {
                    img: 'img/category-image-03-446x550_t.jpg',
                    name: 'Dragonball'
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

.card {
    position: relative;
    background-color: transparent;

    .card-image {
        width: 100%;
        height: 100%;
    }

    .card-body {
        background-color: rgba(0, 0, 0, 0.5);
        position: absolute;
        right: 0;
        left: 0;
        bottom: 0;
        z-index: 1000;
        transition: background-color 1s;

        a {
            color: $secondary-color;
        }
    }

    button {
        position: absolute;
        left: 50%;
        top: 50%;
        padding: .7rem;
        border: 0;
        background-color: $main-color;
        color: $secondary-color;
        opacity: 0;
        transition: 1.5s;
        translate: -50% -50%;
    }

    &:hover {
        .card-body {
            background-color: $main-color;
        }

        button {
            opacity: 1;
        }
    }


}
</style>