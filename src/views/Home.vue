<template>
    <div id="home-page">
        <a id="top"></a>
        <AppearAnimate :delay="navbarDelay" :transition="[0,'-60px']">
            <NavbarComp id="navbar" v-show="showNav" :class="{change_background: scrollPosition > 140}" />
        </AppearAnimate>
        <div id="hero-section">
            <HeroComp />
        </div>
        <AboutComp id="about-section" />
        <ProjectComp id="project-section" />
        <ContactForm id="contact-form" />
        <AppearAnimate :delay="3500" :transition="[0,'100px']">
            <ContactMeBtn />
        </AppearAnimate>
        <BottomFooter />
    </div>
</template>

<script>
import HeroComp from '../components/HeroComp.vue'
import NavbarComp from '../components/NavbarComp.vue'
import AboutComp from '../components/AboutComp.vue'
import AppearAnimate from '../components/AppearAnimate.vue'
import ProjectComp from '../components/ProjectComp.vue'
import ContactForm from '../components/ContactForm.vue'
import ContactMeBtn from '../components/ContactMeBtn.vue'
import BottomFooter from '../components/BottomFooter.vue'

    export default {
        name: "Home",
        components: {
            HeroComp,
            NavbarComp,
            AboutComp,
            AppearAnimate,
            ProjectComp,
            ContactForm,
            ContactMeBtn,
            BottomFooter
        },
        mounted() {
            window.addEventListener('scroll', this.updateScroll);

            window.addEventListener('scroll', () => {
                // detects new state and compares it with the old one
                if ((document.body.getBoundingClientRect()).top > this.scrollPos) {
                    this.showNav = true;
                }
                else
                {
                    this.showNav = false;
                }
                // saves the new position for iteration.
                this.scrollPos = (document.body.getBoundingClientRect()).top;
            })
        },
        beforeDestroy() {
            window.removeEventListener('scroll', this.updateScroll); // To avoid memory leakage
        },
        data() {
            return {
                scrollPosition: 0,
                scrollPos: 0,
                showNav: true,
                navbarDelay: 2700,
            }
        },
        methods: {
            updateScroll() {
            this.scrollPosition = window.scrollY;
            this.navbarDelay = 10;
            },
        },
    }
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Proza+Libre:wght@700&display=swap');

    #home-page {
        width: 100vw;
        height: fit-content;
        background: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.1)), url('~@/assets/heroimage.jpg');
        background-repeat: no-repeat;
        background-size: cover;
        background-attachment: fixed;
        background-position: center;
        display: grid;

        #top {
            display: none;
        }

        .change_background {
            background: rgba(0,0,0,0.9);
            box-shadow: 0 2px 4px 0 rgba(0,0,0,.6);
        }

        #navbar {
            position: fixed;
            height: 8vh;
            z-index: 99;
        }

        #hero-section {
            margin-top: 8vh;
            display: grid;
        }

        #about-section {
            justify-self: center;
        }

        #contact-form {
            height: fit-content;
        }
    }

    @media screen and (min-width: 1100px) {
        #home-page {
            .change_background {
                background: rgba(0,0,0,1);
            }
        }
    }
</style>

