<template>
    <div id="hero" class="d-flex align-items-center">
        <div class="myContainer">
            <div class="d-flex flex-column w-25">

                <div class="upcoming">
                    <h4 class="m-0">Upcoming Stock</h4>
                </div>

                <div class="text-white mt-3 mb-5">
                    <h1>Resident Evil 3 Remake</h1>
                </div>

                <div>
                    <button class="btn rounded-0 fw-bold">Shop Now</button>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'JumbotronComponent'
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

#hero {
    width: 100%;
    height: 600px;
    background-image: url('img/parallax.jpg');
    background-size: cover;
    background-position: center;



    .btn {
        background-color: $light-color;

        &:hover {
            background-color: $secondary-color;
        }
    }
}
</style>