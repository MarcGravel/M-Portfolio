<template>
    <div id="hero-container">
        <div id="hero-info">
            <AppearAnimate :delay="700" :transition="['140vw', 0]">
            <h1 id="name">Marc Gravel</h1>
            </AppearAnimate>
            <AppearAnimate :delay="1100" :duration="2000">
            <h2 id="position">Full-stack Developer</h2>
            </AppearAnimate>
        </div>
        <div id="techs">
            <AppearAnimate :delay="2150" :transition="[0, '-50vh']">
                <div id="python" class="techType">
                    <img src="@/assets/python.svg" alt="Python Logo">
                    <h4>Python</h4>
                </div>
            </AppearAnimate>
            <AppearAnimate :delay="2100" :transition="[0, '-50vh']">
                <div id="javascript" class="techType">
                    <img src="@/assets/javascript.svg" alt="Javascript Logo">
                    <h4>JavaScript</h4>
                </div>
            </AppearAnimate> 
            <AppearAnimate :delay="2250" :transition="[0, '-50vh']">
                <div id="vue" class="techType">
                    <img src="@/assets/vue.svg" alt="vue.js Logo">
                    <h4>Vue.js</h4>
                </div>
            </AppearAnimate>
            <AppearAnimate :delay="2500" :transition="[0, '-50vh']">
                <div id="html5" class="techType">
                    <img src="@/assets/html5.svg" alt="Html Logo">
                    <h4>HTML</h4>
                </div>
            </AppearAnimate>
            <AppearAnimate :delay="2300" :transition="[0, '-50vh']">
                <div id="css3" class="techType">
                    <img src="@/assets/css3.svg" alt="Css Logo">
                    <h4>CSS</h4>
                </div>
            </AppearAnimate>
            <AppearAnimate :delay="2450" :transition="[0, '-50vh']">
                <div id="node" class="techType">
                    <img src="@/assets/node-js.svg" alt="Node.js Logo">
                    <h4>Node.js</h4>
                </div>
            </AppearAnimate>
            <AppearAnimate :delay="2050" :transition="[0, '-50vh']">
                <div id="csharp" class="techType">
                    <img src="@/assets/csharp.svg" alt="csharp Logo">
                    <h4>C#</h4>
                </div>
            </AppearAnimate>
            <AppearAnimate :delay="2200" :transition="[0, '-50vh']">
                <div id="flask" class="techType">
                    <img src="@/assets/flask.png" alt="Flask Logo">
                    <h4 id=flask-tag>Flask</h4>
                </div>
            </AppearAnimate>
            <AppearAnimate :delay="2350" :transition="[0, '-50vh']">
                <div id="apache" class="techType">
                    <img src="@/assets/apache.svg" alt="Apache Logo">
                    <h4>Apache</h4>
                </div>
            </AppearAnimate>
            <AppearAnimate :delay="2000" :transition="[0, '-50vh']">
                <div id="maria" class="techType">
                    <img src="@/assets/mariadb.svg" alt="mariaDB Logo">
                    <h4>MariaDB</h4>
                </div>
            </AppearAnimate>
        </div>
    </div>
</template>

<script>
import AppearAnimate from '../components/AppearAnimate.vue'

    export default {
        name: "HeroComp",
        components: {
            AppearAnimate,
        },
        mounted() {
            this.show = true;
        },
        data() {
            return {
                show: false,
            }
        }
    }
</script>

<style lang="scss" scoped>

    #hero-container {
        background: transparent;
        width: 100vw;
        height: 92vh;
        display: grid;
        grid-template-rows: 46vh 46vh;
        justify-items: center;
        align-items: center;

        #hero-info {
            grid-row: 1;
            text-align: center;
            color: whitesmoke;
            opacity: 0.8;
            width: 100%;
            margin-top: 5vh;

            #name {
                font-size: 3.5em;
                margin-bottom: 4vh;
            }
        }

        #techs {
            grid-row: 2;
            width: 100%;
            height: 100%;
            display: grid;
            justify-items: center;
            grid-template-rows: 50% 50%;
            grid-template-columns: repeat(5, 20%);

            .techType {
                display: grid;
                justify-items: center;
                height: 50px;
                width: 75px;

                img {
                    width: 50px;
                    align-self: end;
                }

                h4 {
                    margin-top: 1vh;
                    text-align: center;
                    color: whitesmoke;
                }
            }

            #python {
                grid-area: 2 / 2;
                position: relative;
                bottom: 6vh;
                right: 5vw;
            }

            #javascript {
                grid-area: 2 / 3;
                position: relative;
                top: 3vh;
            }

            #vue {
                grid-area: 1 / 3;
                position: relative;
                top: 9vh;
            }

            #html5 {
                grid-area: 1 / 4;
                position: relative;
                bottom: 4vh;
            }

            #css3 {
                grid-area: 1 / 5;
                position: relative;
                top: 4vh;
            }

            #node {
                grid-area: 1 / 2;
                position: relative;
                bottom: 4vh;
            }

            #csharp {
                grid-area: 2 / 5;
                position: relative;
                top: 6vh;
                right: 1vw;
            }

            #flask {
                grid-area: 2 / 4;
                position: relative;
                bottom: 6vh;
                left: 5vw;
                filter: invert(100%);

                #flask-tag {
                    filter: invert(100%)
                }
            }

            #apache {
                grid-area: 1 / 1;
                position: relative;
                top: 4vh;
            }

            #maria {
                grid-area: 2 / 1;
                position: relative;
                top: 8vh;
            }
        }
    }

    @media screen and (max-width: 390px) {
        #hero-container {
            #techs {
                .techType {
                    height: 30px;
                    width: 50px;

                    img {
                        width: 30px;
                    }
                }

                #javascript {
                    right: 3.5vw;
                }
            }
        }
    }

    @media screen and (min-width: 700px) {
        #hero-container {
            width: 80%;
            justify-self: center;

            #hero-info {

                #name {
                    font-size: 5em;
                }

                #position {
                    font-size: 2em;
                }
            }
            
        }
    }

    @media screen and (min-width: 1100px) {
        #hero-container {
            width: 70%;
            
            #techs {
                width: 60%;
                height: 80%;
                #python {
                    bottom: 0;
                    right: 0;
                }

                #javascript {
                    top: 0;
                }

                #vue {
                    top: 0;
                }

                #html5 {
                    bottom: 0;
                }

                #css3 {
                    top: 0;
                }

                #node {
                    bottom: 0;
                }

                #csharp {
                    top: 0;
                    right: 0;
                }

                #flask {
                    bottom: 0;
                    left: 0;
                }

                #apache {
                    top: 0;
                }

                #maria {
                    top: 0;
                }
            }
        }
    }
</style>