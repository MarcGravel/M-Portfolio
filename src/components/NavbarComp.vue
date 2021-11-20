<template>
    <div id="navbar">
        <!--Code for mobile and tablet view-->
        <v-icon id="icon" @click="openDrawer">{{hambIcon}}</v-icon>
        <v-navigation-drawer
            id="nav-drawer"
            v-model="navDrawer"
            absolute
            color="#2b2b2b">

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
            id="top-btn"
            class="nav-btns"
            plain
            dark
            @click="pushAnchor('Top')"
            >
            Top
            </v-btn>
            <div class="break-line"></div>
            <v-btn
            class="nav-btns"
            plain
            dark
            @click="pushAnchor('About Me')"
            >
            About Me
            </v-btn>
            <div class="break-line"></div>
            <v-btn
            class="nav-btns"
            plain
            dark
            @click="pushAnchor('Projects')"
            >
            Projects
            </v-btn>
            <div class="break-line"></div>
            <v-btn
            class="nav-btns"
            plain
            dark
            @click="pushAnchor('Contact Me')"
            >
            Contact
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
                    { title: 'Projects', icon: "code" },
                    { title: 'Contact Me', icon: "chat_bubble_outline" },
                ],
            }
        },
        methods: {
            pushAnchor(title) {
                if(title == "Top") {
                    window.scrollTo({top: 0, behavior: 'smooth'});
                    this.navDrawer = false;
                    this.$emit('hideNav');
                }
                else if(title == "About Me") {
                    let currentPos = document.body.getBoundingClientRect().top;
                    let elPos = document.getElementById("about-section").getBoundingClientRect().top;
                    if (currentPos > elPos) {
                        document.getElementById("about-section").scrollIntoView();
                    }
                    else {
                        let yOffset = -40;
                        let elm = document.getElementById("about-section");
                        let adj = elm.getBoundingClientRect().top + window.pageYOffset + yOffset;

                        window.scrollTo({top: adj, behavior: 'smooth'});
                    }
                    this.navDrawer = false;
                }
                else if(title == "Projects") {
                    let currentPos = document.body.getBoundingClientRect().top;
                    let elPos = document.getElementById("project-section").getBoundingClientRect().top;
                    if (currentPos > elPos) {
                        document.getElementById("project-section").scrollIntoView();
                    }
                    else {
                        let yOffset = -50;
                        let elm = document.getElementById("project-section");
                        let adj = elm.getBoundingClientRect().top + window.pageYOffset + yOffset;

                        window.scrollTo({top: adj, behavior: 'smooth'});
                    }
                    this.navDrawer = false;
                }
                else if(title == "Contact Me") {
                    let currentPos = document.body.getBoundingClientRect().top;
                    let elPos = document.getElementById("contact-form").getBoundingClientRect().top;
                    if (currentPos > elPos) {
                        document.getElementById("contact-form").scrollIntoView();
                    }
                    else {
                        let yOffset = -40;
                        let elm = document.getElementById("contact-form");
                        let adj = elm.getBoundingClientRect().top + window.pageYOffset + yOffset;

                        window.scrollTo({top: adj, behavior: 'smooth'});
                    }
                    this.navDrawer = false;
                } 
                
            },
            openDrawer() {
                this.navDrawer = true;
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
                color: #868686;
                border-bottom: 1px black solid;
                background-color: #474853;
                

                #bar-elem-container {
                    display: grid;
                    grid-template-columns: 20% 80%;
                    
                    #drawer-icon, #drawer-title {
                        font-size: 1.5em;
                        color: #86b3d1;
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
                grid-template-columns: 24% 1% 24% 1% 24% 1% 24%;
                width: 90%;
                justify-self: center;
                justify-items: center;

                .nav-btns {
                    font-weight: bold;
                    color: #86b3d1;
                    font-size: 2em;
                }

                .break-line {
                    width: 10%;
                    height: 50%;
                    background-color: whitesmoke;
                    opacity: 0.7;
                }
            }
        }
    }

    @media screen and (min-width: 1400px) {
        #navbar {
            #desktop-btn-container {
                width: 70%;
            }
        }
    }

    @media screen and (min-width: 1900px) {
        #navbar {
            #desktop-btn-container {
                width: 60%;
            }
        }
    }
</style>