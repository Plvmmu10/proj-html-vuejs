<template>
    <div class="myContainer">
        <div class="d-flex flex-column align-items-center pb-4">
            <h1 class="text-white">New Game Blogs</h1>
            <div class="horizontal"></div>
        </div>

        <div class="position-relative">
            <div class="row d-flex flex-nowrap" ref="sliderBox">
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

            <!-- Change slide buttons -->
            <button class="prevBtn myBtn" @click="prevCard">
                <i class="fa-solid fa-chevron-left"></i>
            </button>

            <button class="nextBtn myBtn" @click="nextCard">
                <i class="fa-solid fa-chevron-right"></i>
            </button>
        </div>


        <div class="row d-flex py-5">
            <div class="brand-container" v-for="image in teamImages">
                <div class="brand-box">
                    <img :src="image">
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
                },
                {
                    img: 'img/Architecto-beatae-vitae-dicta.jpg',
                    date: 'Jan 25,2021',
                    text: 'Anyway REPS is a NYC agency repres enting photographers'
                },
                {
                    img: 'img/Blandit-praesen-volupta.jpg',
                    date: 'Jan 18,2021',
                    text: 'Anyway REPS is a NYC agency repres enting photographers'
                },
            ],
            teamImages: [
                'img/brand-01.png',
                'img/brand-02.png',
                'img/brand-03.png',
                'img/brand-04.png',
                'img/brand-05.png',
            ],

            status: false,
            container: null,
            containerWidth: null
        }
    },
    methods: {
        setActive() {
            this.status = !this.status
        },
        nextCard() {
            this.container.scrollBy(this.containerWidth / 3, 0);


            if ((this.container.scrollLeft + this.containerWidth + 2) >= this.container.scrollWidth) {
                this.container.scrollLeft = 0
            }
        },
        prevCard() {
            this.container.scrollBy(- this.containerWidth / 3, 0);

            if (this.container.scrollLeft === 0) {
                this.container.scrollLeft = this.container.scrollWidth
            }
        }
    },
    mounted() {
        this.container = this.$refs.sliderBox;
        this.containerWidth = this.container.offsetWidth
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

.brand-container {
    width: calc(100% / 5);
    opacity: .5;

    &:hover {
        opacity: 1;
        scale: 1.5;
        transition: 1s;
    }
}

.active {
    opacity: 1;
}

.myBtn {
    width: 35px;
    height: 35px;
    border-radius: 50%;
    background-color: transparent;
    border: 1px solid rgb(211, 211, 211, 1);
    color: rgb(211, 211, 211, 1);
    display: flex;
    align-items: center;
    justify-content: center;
    transition: .3s;

    i {
        font-size: 15px;
    }

    &:hover {
        color: $secondary-color;
        background-color: $light-color;
    }
}

.prevBtn {
    position: absolute;
    left: -2%;
    bottom: 50%;
    z-index: 1000;
    translate: 0% -80%;
}

.nextBtn {
    position: absolute;
    right: -2%;
    bottom: 50%;
    translate: 0% -80%;
}

.row {
    overflow-x: auto;
    overflow-y: hidden;

    // Scrollbar config
    &::-webkit-scrollbar {
        display: none;
    }

    -ms-overflow-style:none;

    scrollbar-width:none;

    scroll-behavior: smooth;

}
</style>