<template>
    <div id="navbar">
        <!--Code for mobile and tablet view-->
        <v-icon id="icon" @click="openDrawer">{{hambIcon}}</v-icon>
        <v-navigation-drawer
            id="nav-drawer"
            v-model="navDrawer"
            absolute
            color="#474853">

            <h1 id="drawer-logo">M.G</h1>
            <hr>

            <v-list-item id="list-item"
                v-for="item in items"
                :key="item.title"
                :to="item.route"
                link
                @click="pushAnchor(item.title); openDrawer"
                >
                <div id="bar-elem-container">
                    <v-list-item-icon>
                        <v-icon id="drawer-icon" color="#86b3d1">{{ item.icon }}</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                        <v-list-item-title id="drawer-title">{{item.title}}</v-list-item-title>
                    </v-list-item-content>
                </div>
            </v-list-item>
        </v-navigation-drawer>
        <!--Code for desktop view-->
        <div id="desktop-btn-container">
            <v-btn
            class="nav-btns"
            plain
            dark
            @click="pushAnchor('Top')"
            >
            Top
            </v-btn>
            <v-btn
            class="nav-btns"
            plain
            dark
            @click="pushAnchor('About Me')"
            >
            About Me
            </v-btn>
        </div>
    </div>
</template>

<script>
    export default {
        name: "NavbarComp",
        data() {
            return {
                hambIcon: "menu",
                navDrawer: false,
                items: [
                    { title: 'Top', icon: "arrow_upward" },
                    { title: 'About Me', icon: "person_pin" },
                ],
            }
        },
        methods: {
            pushAnchor(title) {
                if(title == "Top") {
                    window.scrollTo({top: 0, behavior: 'smooth'});
                    this.navDrawer = !this.navDrawer;
                }
                else if(title == "About Me") {
                    document.getElementById("about-section").scrollIntoView();
                    this.navDrawer = !this.navDrawer;
                } 
                
            },
            openDrawer() {
                this.navDrawer = !this.navDrawer;
            },
        }
    }
</script>

<style lang="scss" scoped>
    #navbar {
        height: 100%;
        width: 100vw;
        display: grid;

        #desktop-btn-container {
            display: none;
        }

        #icon {
            color: #86b3d1;
            font-size: 3.5em;
            justify-self: start;
            align-self: center;
            margin-left: 10px;
        }

        #nav-drawer {
            position: fixed;
            height: 100vh;
            color: #86b3d1;

            #drawer-logo {
                margin: 4vh 0 1vh 0;
                font-size: 3em;
                font-family: 'Raleway', sans-serif;
            }
            
            hr {
                width: 70%;
                margin-left: 15%;
                margin-bottom: 2vh;
            }

            #list-item {
                color: #86b3d1;
                border-bottom: 1px black solid;
                background-color: #5f6070;
                

                #bar-elem-container {
                    display: grid;
                    grid-template-columns: 20% 80%;
                    
                    #drawer-icon, #drawer-title {
                        font-size: 1.5em;
                    }
                }
            }
        }
    }

    @media screen and (min-width: 1100px) {
        #navbar {
            background: rgba(0,0,0,1);
            box-shadow: 0 2px 4px 0 rgba(0,0,0,.6);

            #icon {
                display: none;
            }

            #nav-drawer {
                display: none;
            }

            #desktop-btn-container {
                display: grid;
                justify-items: center;
                align-items: center;
                grid-template-columns: 50% 50%;
                width: 40%;
                justify-self: center;

                .nav-btns {
                    font-weight: bold;
                    color: #86b3d1;
                    font-size: 2em;
                }
            }
        }
    }
</style>