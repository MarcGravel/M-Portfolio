<template>
    <div id="home-page">
        <Appear :delay="1500" :transition="[0,'-60px']">
            <Navbar id="navbar" :class="{change_background: scrollPosition > 50}" />
        </Appear>
        <Hero />
        <About id="about-section" />
    </div>
</template>

<script>
import Hero from '../components/Hero.vue'
import Navbar from '../components/Navbar.vue'
import About from '../components/About.vue'
    export default {
        name: "Home",
        components: {
            Hero,
            Navbar,
            About,
        },
        mounted() {
            window.addEventListener('scroll', this.updateScroll);
        },
        data() {
            return {
                scrollPosition: null,
            }
        },
        methods: {
            updateScroll() {
            this.scrollPosition = window.scrollY
            }
        }
    }
</script>

<style lang="scss" scoped>
    #home-page {
        width: 100vw;
        height: fit-content;
        background: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.1)), url('~@/assets/heroimage.jpg');
        background-repeat: no-repeat;
        background-size: cover;
        background-attachment: fixed;
        background-position: center;
        display: grid;

        .change_background {
            background: rgba(0,0,0,0.9);
            box-shadow: 0 2px 4px 0 rgba(0,0,0,.6);
        }

        #navbar {
            position: sticky;
            top: 0;
            z-index: 99;
        }

        #about-section {
            justify-self: center;
            border-radius: 5px;
        }
    }
</style>

