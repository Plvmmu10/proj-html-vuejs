<template>
    <div class="col-3">
        <div class="card border-0 rounded-0">
            <div class="card-image">
                <img :src="item.img" :alt="item.name" class="w-100 h-100">
            </div>

            <!-- Card body with rating, name and price -->
            <div class="card-body" @click="changeStatus">
                <i class="fa-star" v-for="star in 5" :class="(star <= item.rating ? 'fa-solid' : 'fa-regular')"></i>

                <p class="text-white m-0">{{ item.name }}</p>

                <div class="price-box d-flex" :class="status ? 'active' : 'deactive'">
                    <p class="discount m-0 pe-2" v-if="item.firstPrice != ''">&pound;{{ item.firstPrice }}</p>
                    <p class="price m-0">&pound;{{ item.secondPrice }}</p>
                </div>

                <div class="options-box" :class="!status ? 'active' : 'deactive'">
                    <ul class="d-flex p-0 w-100">
                        <li>
                            <i class="fa-solid fa-bag-shopping"></i>
                        </li>

                        <li>
                            <i class="fa-solid fa-heart"></i>
                        </li>

                        <li>
                            <i class="fa-solid fa-maximize"></i>
                        </li>

                        <li>
                            <i class="fa-solid fa-eye"></i>
                        </li>
                    </ul>
                </div>

            </div>


        </div>
    </div>
</template>

<script>
export default {
    name: 'SliderCard',
    props: ['item'],
    data() {
        return {
            status: true
        }
    },
    methods: {
        changeStatus() {
            this.status = !this.status
            console.log(this.status)
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

.card-body {
    background-color: rgb(21, 17, 29);
    position: relative;

    .fa-star {
        color: $secondary-color;
    }

    .discount {
        text-decoration: line-through;
        color: rgb(211, 211, 211, 0.6);
    }

    .price {
        color: $secondary-color;
    }

}

.options-box {
    width: 100%;
    position: absolute;
    bottom: -15%;
    left: 0;

    li {
        width: 100%;
        height: 100%;
        color: $light-color;
        text-align: center;
        padding: .5rem;
        border: 1px solid rgba(211, 211, 211, 0.2);

        &:hover {
            color: $secondary-color;
        }
    }
}


.active {
    opacity: 1;
}

.deactive {
    opacity: 0;
}
</style>