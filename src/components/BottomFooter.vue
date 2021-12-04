<template>
    <div id="footer">
        <div id="foot-links">
            <a class="foot-tag" href="https://www.linkedin.com/in/marc-gravel-1208061ba/" target="_blank">LinkedIn</a>
            <p class="foot-tag">&nbsp;-&nbsp;</p>
            <a class="foot-tag" href="https://github.com/MarcGravel" target="_blank">Github</a>
            <p class="foot-tag">&nbsp;-&nbsp;</p>
            <a class="foot-tag" href="mailto:gravel.m@outlook.com" target="_blank">gravel.m@outlook.com</a>
            <p class="foot-tag">&nbsp;-&nbsp;</p>
            <v-menu
                v-model="menu"
                absolute
                :close-on-content-click="false"
                :nudge-width="200"
                transition="slide-y-transition"
                >
                <template v-slot:activator="{ on, attrs }">
                    <p 
                        id="attributes"
                        class="foot-tag"
                        v-bind="attrs"
                        v-on="on"
                        >
                        Attributes
                        </p>
                </template>
                <v-card id="card">
                    <v-list>
                    <v-list-item>
                        <v-list-item-content>
                        <v-list-item-title>Tech logo attributes</v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                    </v-list>

                    <v-divider></v-divider>

                    <v-list>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/python" target="_blank">Python Icon</a> by 
                            <a href="https://iconscout.com/contributors/icon-mafia" target="_blank">Icon Mafia</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/javascript" target="_blank">Javascript Icon</a> by <a href="https://iconscout.com/contributors/icon-mafia" target="_blank">Icon Mafia</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/csharp" target="_blank">Csharp Icon</a> by <a href="https://iconscout.com/contributors/icon-mafia" target="_blank">Icon Mafia</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/vue-dot-js" target="_blank">Vue Dot Js Icon</a> by <a href="https://iconscout.com/contributors/icon-54" target="_blank">Icon 54</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/flask" target="_blank">Flask Logo Icon</a> by <a href="https://iconscout.com/contributors/icon-mafia" target="_blank">Icon Mafia</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/node-js" target="_blank">Node Js Logo Icon</a> by <a href="https://iconscout.com/contributors/icon-54" target="_blank">Icon 54</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/mariadb" target="_blank">Mariadb Icon</a> by <a href="https://iconscout.com/contributors/icon-mafia" target="_blank">Icon Mafia</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/react" target="_blank">React Icon</a> by <a href="https://iconscout.com/contributors/icon-mafia" target="_blank">Icon Mafia</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/html5" target="_blank">Html5 Icon</a> by <a href="https://iconscout.com/contributors/icon-mafia" target="_blank">Icon Mafia</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p><a href="https://iconscout.com/icons/css3" target="_blank">Css3 Icon</a> by <a href="https://iconscout.com/contributors/icon-mafia" target="_blank">Icon Mafia</a></p>
                        </v-list-item>
                        <v-list-item class="att-list-items">
                            <p>SQL Icon by <a href="https://www.flaticon.com/authors/pixel-perfect" target="_blank">Pixel perfect</a> from <a href="https://www.flaticon.com/" target="_blank">www.flaticon.com</a></p>
                        </v-list-item>
                    </v-list>
                    <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn
                        text
                        color="error"
                        @click="menu = false"
                    >
                        Close
                    </v-btn>
                    </v-card-actions>
                </v-card>
            </v-menu>
        </div>
        <div id="copyright">
            <p class="foot-tag">© 2021 - Web design by Marc Gravel</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "BottomFooter",
        data() {
            return {
                menu: false,
            }
        }
    }
</script>

<style lang="scss" scoped>
    #footer {
        width: 100%;
        height: 10vh;
        background-color: black;
        z-index: 60;
        display: grid;
        justify-items: center;
        align-items: center;

        #foot-links {
            height: 2vh;

            .foot-tag {
                display: inline-block;
                color: whitesmoke;
                text-decoration: none;
            }

            a:hover {
                text-decoration: underline;
            }

            #attributes:hover {
                cursor: pointer;
                text-decoration: underline;
            }
        }

        #copyright {
            color: whitesmoke;
            opacity: 0.7;
        }
    }

    #card > *{
        background-color: rgb(224, 223, 223);
    }

    .att-list-items > p {
        height: fit-content;
        margin-bottom: 0;
    }

    @media screen and (max-width: 400px) {
        #footer {

            #foot-links {
                a, p {
                    font-size: 0.8em
                }
            }

            #copyright > p {
                font-size: 0.8em
            }
        }
    }

    @media screen and (max-width: 350px) {
        #footer {

            #foot-links {
                a, p {
                    font-size: 0.7em
                }
            }

            #copyright > p {
                font-size: 0.7em
            }
        }
    }

    @media screen and (max-width: 300px) {
        #footer {

            #foot-links {
                a, p {
                    font-size: 0.6em
                }
            }

            #copyright > p {
                font-size: 0.6em
            }
        }
    }
</style>