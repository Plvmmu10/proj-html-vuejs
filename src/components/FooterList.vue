<template>
    <div class="col-3">
        <h4>Address Info</h4>

        <ul class="subtitle">
            <li id="address">
                <p>
                    60 29th Street San Francisco, CA 94110 507-Union Trade Center, United States of America
                </p>
            </li>

            <li id="number">
                <p>
                    (+00) 123-456-789
                </p>
            </li>

            <li id="email">
                <p>
                    demo@example.com
                </p>
            </li>
        </ul>
    </div>

    <div class="col-3" v-for="item in footerArray">
        <h4>{{ item.title }}</h4>

        <ul>
            <li v-for="listItem in item.liList">
                <a href="#">{{ listItem }}</a>
            </li>
        </ul>
    </div>

    <!-- Newsletter col -->
    <div class="col-3">
        <h4>Our Newsletter</h4>

        <p class="subtitle">
            There are many variations of passages of form humour or randomised
        </p>


        <div class="d-flex pt-4">
            <input type="text" name="textInput" id="textInput" class="form-control border-0 rounded-0">
            <button class="myBtn p-2">
                <i class="fa-solid fa-paper-plane"></i>
            </button>
        </div>




        <div class="social-box d-flex">
            <p v-for="social in socialArray" class="py-4 px-2"><i :class="social"></i></p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FooterList',
    props: ['footerArray', 'socialArray']
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

h4 {
    color: $light-color;
}

ul {
    padding: 0;

    li {
        display: flex;

        a {
            text-decoration: none;
            color: rgba(211, 211, 211, 0.6);

            &:hover {
                color: $secondary-color;
            }
        }
    }

    #address:before {
        font-family: 'Font Awesome 6 Free';
        content: '\f3c5';
        font-weight: 900;
        margin: 0 15px 0 0px;
        color: $secondary-color;
    }

    #number:before {
        font-family: 'Font Awesome 6 Free';
        content: '\f095';
        font-weight: 900;
        margin: 0 15px 0 0px;
        color: $secondary-color;
    }


    #email:before {
        font-family: 'Font Awesome 6 Free';
        content: '\f0e0';
        font-weight: 900;
        margin: 0 15px 0 0px;
        color: $secondary-color;
    }

    #email:hover {
        cursor: pointer;
        color: $secondary-color;
    }
}

.social-box {
    i {
        color: $light-color;

        &:hover {
            cursor: pointer;
            color: $secondary-color;
        }
    }
}

.myBtn {
    border: 0;

    &:hover {
        color: $secondary-color;
    }
}
</style>