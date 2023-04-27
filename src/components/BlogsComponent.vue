<template>
    <div class="myContainer">
        <div class="d-flex flex-column align-items-center pb-4">
            <h1 class="text-white">New Game Blogs</h1>
            <div class="horizontal"></div>
        </div>

        <div class="row">
            <div class="col-4" v-for="blog in blogsList">
                <div class="card bg-transparent border-0" @click="setActive">

                    <!-- Card header with card image -->
                    <div class="card-header border-0">
                        <img :src="blog.img" class="w-100 h-100">
                    </div>

                    <!-- Card body with card content -->
                    <div class="card-body">
                        <div class="d-flex">
                            <p class="subtitle pe-3">
                                <i class="fa-regular fa-calendar-days"></i> {{ blog.date }}
                            </p>

                            <p class="subtitle">
                                <i class="fa-regular fa-comment"></i> 0 Comment
                            </p>
                        </div>

                        <p class="text-white">{{ blog.text }}</p>
                    </div>

                    <!-- Blog hover actions -->
                    <div class="blog-icons d-flex" :class="status ? 'active' : ''">
                        <div class="icon-box">
                            <i class="fa-solid fa-plus"></i>
                        </div>

                        <div class="icon-box">
                            <i class="fa-solid fa-link"></i>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BlogsComponent',
    data() {
        return {
            blogsList: [
                {
                    img: 'img/At-vero-eos-et-accusamus-1400x878_t.jpg',
                    date: 'Jan 18,2021',
                    text: 'Anyway REPS is a NYC agency repres enting photographers'
                },
                {
                    img: 'img/Rerum-facilis-est-et-exped-1400x878_t.jpg',
                    date: 'Jan 18,2021',
                    text: 'Anyway REPS is a NYC agency repres enting photographers'
                },
                {
                    img: 'img/Nisi-ut-aliquid-ex-ea-com-1400x878_t.jpg',
                    date: 'Jan 18,2021',
                    text: 'Anyway REPS is a NYC agency repres enting photographers'
                }
            ],

            status: false
        }
    },
    methods: {
        setActive() {
            this.status = !this.status
        }
    }
}

</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

i {
    color: $secondary-color;
    padding-right: 2px;
}

.card {
    position: relative;
}

.blog-icons {
    position: absolute;
    top: 25%;
    left: 34%;
    opacity: 0;
    transition: 1.5s;

    .icon-box {
        border-radius: 50%;
        border: 1px solid $light-color;
        width: 50px;
        height: 50px;
        margin: 0 .3rem;

        i {
            color: $light-color;
            padding: 1rem;
        }
    }
}


.active {
    opacity: 1;
}
</style>