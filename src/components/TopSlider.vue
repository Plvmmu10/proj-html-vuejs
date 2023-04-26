<template>
    <div class="d-flex align-items-center justify-content-center py-3">
        <ul class="d-flex">
            <li v-for="listItem in listArray" class="text-white">
                <a href="#">{{ listItem }}</a>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'TopSlider',
    props: [
        'listItem',
        'listArray'
    ]
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

li {
    border: 1px solid rgba(211, 211, 211, 0.2);
    padding: 1rem 2rem;

    a {
        text-decoration: none;
        color: white;
    }

    &:hover {
        cursor: pointer;

        a {
            color: $secondary-color;
        }
    }
}
</style>