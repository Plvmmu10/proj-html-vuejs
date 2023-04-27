<template>
    <div class="myContainer h-100">
        <div class="row flex-nowrap h-100 w-100 overflow-auto">
            <div class="col-12 d-flex align-items-center" v-for="(member, index) in teamList" :key="index">
                <div class="card bg-transparent border-0">
                    <!-- Header of Card with images -->
                    <div class="card-header d-flex justify-content-center border-0">
                        <div class="card-image">
                            <div class="img-box">
                                <img :src="member.img" :alt="member.name">
                            </div>

                            <div class="quote-box">
                                <img src="img/quote.png">
                            </div>
                        </div>
                    </div>

                    <!-- Body of Card with info and text-->
                    <div class="card-body text-center">
                        <div class="role-box">
                            <h5 class="text-white">{{ member.name }} <span class="role">({{ member.role }})</span></h5>
                        </div>

                        <div class="text-box ">
                            <p class="subtitle">
                                Lorem, ipsum dolor sit amet consectetur adipisicing elit. Tempore nulla neque officia earum
                                enim
                                distinctio quod asperiores ipsum unde eos eum, obcaecati quos saepe tenetur.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'OurTeam',
    data() {
        return {
            teamList: [
                {
                    name: 'Luies Charls',
                    role: 'Web Designer',
                    img: 'img/t5-1-100x100_left.jpg'
                },
                {
                    name: 'Pinco Pallo',
                    role: 'Web Developer',
                    img: 'img/t4-1-100x100_left.jpg'
                },
                {
                    name: 'Mario Rossi',
                    role: 'Manager',
                    img: 'img/t2-1-100x100_left.jpg'
                },
            ],
            currentIndex: 0
        }
    },
    methods: {

    }
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

.card-image {
    position: relative;

    .img-box {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        overflow: hidden;
        border: 2px solid $secondary-color;

        img {
            width: 100%;
            height: 100%;
        }
    }

    .quote-box {
        width: 30px;
        height: 30px;
        border-radius: 50%;
        background-color: $secondary-color;
        display: flex;
        align-items: center;
        justify-content: center;
        position: absolute;
        top: 0;
        left: 0;
    }
}

.role {
    color: $secondary-color;
}
</style>