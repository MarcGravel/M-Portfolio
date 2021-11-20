<template>
    <div id="item-container">
        <div id="project">
            <div id="header" :style="{ 'background-color': project.color }" @click="navigateAway()">
                <img :src="require(`@/assets/${project.img}`)" alt="Project image">
            </div>
            <div id="content">
                <div id="title">
                    <h3>{{project.name}}&nbsp;</h3>
                    <h4>{{project.type}}</h4>
                    <p>{{project.buildDate}}</p>
                </div>
                <p id="description">{{project.description}}</p>
                <p id="skills" v-if="project.skills != null">Skills: {{project.skills}}</p>
                <div id="site-link" v-if="project.url != null" class="links">
                    <h4>Website:&nbsp;</h4>
                    <a :href="`${project.url}`" target="_blank">{{project.url}}</a>
                </div>
                <div id="front-link" v-if="project.frontend != null" class="links">
                    <h4>Front-end Code:&nbsp;</h4>
                    <a :href="`${project.frontend}`" target="_blank">{{project.name}} on Github</a>
                </div>
                <div id="back-link" v-if="project.backend != null" class="links">
                    <h4>Back-end Code:&nbsp;</h4>
                    <a :href="`${project.backend}`" target="_blank">{{project.name}} API on Github</a>
                </div>
                <h4 id="additional">{{project.additional}}</h4>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ProjectItem",
        props: ["project"],
        methods: {
            navigateAway() {
                if (this.project.url != undefined) {
                    window.open(this.project.url);
                }
            }
        }
    }
</script>

<style lang="scss" scoped>
    #item-container {
        width: 100%;
        height: fit-content;
        display: grid;
        justify-items: center;
        margin-bottom: 4vh;

        #project {
            width: 100%;
            max-width: 500px;
            height: fit-content;
            padding-bottom: 2vh;
            background: rgb(0,0,0);
            background: radial-gradient(circle, rgba(9,9,9,1) 0%, rgba(9,9,9,0) 150%);
            box-shadow: 2px 0 30px 40px rgba(9,9,9,.4);
            border: 1px solid rgb(37, 37, 37);
            border-bottom-left-radius: 10px;
            border-bottom-right-radius: 10px;
            color: rgba(245, 245, 245, 0.856);

            h3, h4, a, p {
                opacity: 0.9;
            }

            #header {
                width: 100%;
                display: grid;
                padding: 3vh 2vw 0 2vw;
                justify-items: center;
                cursor: pointer;

                img {
                    width: 100%;
                    max-width: 400px;
                    object-fit: cover;
                    border-top-left-radius: 5px;
                    border-top-right-radius: 5px;
                }
            }

            #content {
                padding: 0 3vw 0 3vw;

                #title {
                    padding: 2vh 0 2vh 0;
                    h3, h4 {
                        display: inline-block;
                    }
                }

                #description {
                    text-align: start;

                }

                #skills {
                    text-align: start;
                    font-size: 0.8em;
                    color: rgb(219, 212, 212);
                }
                
                .links {
                    text-align: start;
                    padding-bottom: 1vh;

                    h4, a {
                        display: inline-block;
                    }

                    h4 {
                        color: #a1d3f5;
                    }

                    a {
                        color: whitesmoke;
                        font-size: 0.9em;
                    }
                }

                #additional {
                    margin-top: 2vh;
                    margin-bottom: 5vh;
                    text-align: start;
                    color: #a1d3f5;
                }
            }
        }
    }

    @media screen and (min-width: 700px) {
        #item-container {
            height: 100%;

            #project {
                height: 100%;

                #header {
                    height: 200px;
                    position: relative;
                    overflow: hidden;

                    img {
                        position: absolute;
                        bottom: 0;
                        width: 90%;
                        height: 180px;
                    }
                }
            }
        }
    }

    @media screen and (min-width: 900px) {
        #item-container {
            #project {
                #header {
                    img {
                        width: 350px;
                    }
                }
            }
        }
    }

    @media screen and (min-width: 1200px) {
        #item-container {
            #project {
                #header {
                    img {
                        width: 90%;
                        max-width: 900px;
                    }
                }
            }
        }
    }
</style>