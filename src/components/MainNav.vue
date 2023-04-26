<template>
    <div class="myContainer py-5">
        <ul class="d-flex text-white">
            <li class="d-flex px-4">
                <i class="fa-solid fa-truck pe-3"></i>

                <div>
                    <h6 class="m-0">Free Delivery</h6>
                    <p class="subtitle">Free Shipping On All Order</p>
                </div>
            </li>


            <li class="d-flex px-4">
                <i class="fa-solid fa-sack-dollar pe-3"></i>

                <div>
                    <h6 class="m-0">Money Return</h6>
                    <p class="subtitle">Back Guarantee in 7 days</p>
                </div>
            </li>



            <li class="d-flex px-4">
                <i class="fa-solid fa-tag pe-3"></i>

                <div>
                    <h6 class="m-0">Member Discount</h6>
                    <p class="subtitle">On every order over &dollar;130.00</p>
                </div>
            </li>


            <li class="d-flex px-4">
                <i class="fa-solid fa-hand-holding-dollar pe-3"></i>

                <div>
                    <h6 class="m-0">Return Policy</h6>
                    <p class="subtitle">Support 24 hours a day</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'MainNav',
    data() {
        return
    }
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

i {
    font-size: 35px;
}

li:hover {
    cursor: pointer;

    i,
    h6 {
        color: $secondary-color;
    }

    p {
        color: $light-color;
    }

}
</style>