<template>
    <div id="navbar">
        <div id="hamb-container">
            <input type="checkbox" id="toggle" @click="openDrawer">
            <label id="hamburger" for="toggle"></label>
        </div>
        
        <v-navigation-drawer
            id="navDrawer"
            v-model="navDrawer"
            absolute
            temporary
            bottom
            color="#f5fffd"
            width="70%"
            height="fit-content">

            <v-list-item id="listItem"
                v-for="item in items"
                :key="item.title"
                :to="item.route"
                :color="item.color"
                link
                >
                <v-btn id="buttons"
                :color="item.color"
                @click="redirectLogout(item.title)">
                    <v-icon>{{ item.icon }}</v-icon>
                    <h2>{{item.title}}</h2>
                </v-btn>
            </v-list-item>

        </v-navigation-drawer>
    </div>
</template>

<script>
import router from '../router'

    export default {
        name: "Navbar",
        data() {
            return {
                navDrawer: null,
                items: [
                    { title: 'Home', icon: 'event_note', route: '/', color: '#57bba5' },
                    { title: 'About Me', icon: 'construction', route: '/#about-section', color: '#57bba5' },
                ],
            }
        },
        methods: {
            goToAbout() {
                router.push('#about-section')
            },
            openDrawer() {
                this.navDrawer = !this.navDrawer;
            },
        }
    }
</script>

<style lang="scss" scoped>
    #navbar {
        height: 8vh;
        width: 100vw;

        #hamb-container {
            height: 100%;
            width: 100%;
            display: grid;
            grid-template-columns: 70px auto;
            align-items: center;

            #toggle {
                display: none;
            }

            #hamburger {
                grid-column: 1;
                justify-self: center;
                width: 40px;
                height: 4px;
                align-self: center;
                border-top: 2px transparent;
                border-bottom: 2px transparent;
                border-radius: 15px;
                background-color: whitesmoke;
                opacity: 0.9;
                z-index: 5;
                
                &::before, &::after {
                    content: '';
                    width: 40px;
                    height: 4px;
                    border-radius: 9px;
                    display: block;
                    position: relative;
                    transition: all 0.6s cubic-bezier(1,0,0,1);
                }

                &::before {
                    background-color: whitesmoke;
                    top: -10px;
                    transform-origin: left top;
                }

                &::after {
                    background-color: whitesmoke;
                    top: 6px;
                    transform-origin: left bottom;
                }
            }

            #toggle:checked ~ label::before {
                background-color: whitesmoke;
                width: 30px;
                transform: rotate(45deg)
            }

            #toggle:checked ~ label::after {
                background-color: whitesmoke;
                width: 30px;
                transform: rotate(-45deg);
            }

            #toggle:checked ~ label {
                background-color: transparent;
            }

            #toggle ~ label {
                transition: all 0.6s cubic-bezier(1,0,0,1);
            }
        }
    }
</style>