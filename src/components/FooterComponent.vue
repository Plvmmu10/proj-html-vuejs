<template>
    <div class="row myContainer py-5">
        <FooterList :footerArray="footerList" :socialArray="socialList" />
    </div>

    <hr style="height: 10px; color: white;">

    <BottomFooter />
</template>

<script>
import FooterList from './FooterList.vue';
import BottomFooter from './BottomFooter.vue';
export default {
    name: 'FooterComponent',
    components: {
        FooterList,
        BottomFooter
    },
    data() {
        return {
            footerList: [
                {
                    title: 'Information',
                    liList: [
                        'Bookmark',
                        'Features',
                        'Sitemap',
                        'Lists',
                        'Contact Us'
                    ]
                },
                {
                    title: 'Extras',
                    liList: [
                        'Delivery',
                        'Cart',
                        'Terms conditions',
                        'My account',
                        'About us'
                    ]
                }
            ],
            socialList: [
                'fa-brands fa-facebook',
                'fa-brands fa-twitter',
                'fa-brands fa-google-plus-g',
                'fa-brands fa-skype',
                'fa-brands fa-instagram'
            ]
        }
    }
}
</script>

<style lang="scss" scoped></style>