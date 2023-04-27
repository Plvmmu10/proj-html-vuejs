<template>
    <div class="text-white myContainer d-flex justify-content-between align-items-center">
        <div>
            <p class="subtitle">Copyright &copy; 2023 Codezeel</p>
        </div>

        <div class="fs-1">
            <i class="fa-brands fa-cc-paypal"></i>
            <i class="fa-brands fa-cc-mastercard px-2"></i>
            <i class="fa-brands fa-cc-visa"></i>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BottomFooter'
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

i {
    cursor: pointer;
    color: white;

    &:hover {
        color: $secondary-color;
    }
}
</style>