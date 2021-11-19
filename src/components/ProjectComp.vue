<template>
    <div id="project-section">
        <div id="project-container">
            <h1 id=proj-title>Projects</h1>
            <div v-for="project in allProjects" :key="project.name" class="project-items">
                <ProjectItem :project="project" />
            </div>
            <GitLinkBtn id="git-link" />
        </div>
    </div>
</template>

<script>
import GitLinkBtn from '../components/GitLinkBtn.vue'
import ProjectItem from '../components/ProjectItem.vue'

    export default {
        name: "ProjectComp",
        components: {
            GitLinkBtn,
            ProjectItem
        },
        data() {
            return {
                allProjects: {
                    jobjug: {
                        name: "JobJug",
                        color: "#86b3d1",
                        type: "- Project Management",
                        buildDate: "Oct-Nov 2021",
                        url: "https://jobjug.ca",
                        img: "jobjugScreen.png",
                        description: "JobJug is a project management web application meant for internal use between employees, managers, and admins. There is no ability to sign up for security purposes. All new users are created within the logged in app by existing managers or admin. JobJug allows users to log in to their personal profile to get up to date info about the companies current and past projects. The site is equipped with automatic invoicing and email services. JobJug is mobile, tablet, and desktop friendly.",
                        frontend: "https://github.com/MarcGravel/JobJug",
                        backend: "https://github.com/MarcGravel/JobJugBackendApi",
                        skills: "JavaScript, Vue.js, HTML, CSS, SASS, Python, Flask, MariaDB, SQL, Apache, Node.js, PM2",
                        additional: "For security reasons, please contact me directly for a temporary account to view and enjoy the site.",
                    },
                    tweeter: {
                        name: "Tweeter",
                        color: "#844d36",
                        type: "- Social Media",
                        buildDate: "Sep-Oct 2021",
                        url: "https://thetweeter.ga",
                        img: "tweeterScreen.png",
                        description: "Tweeter is a social media website based off existing social media services. Tweeter allows users to log-in/sign-up to their own personal profile. From there users are able to edit their profile and add their own personal touch, including photos and bios. Users can create new posts, comment on existing posts, follow other users, and more! To navigate site, use the navigation bars or click on usernames, posts, images, notifications, or any button. Tweeter is mobile, tablet, and desktop friendly.",
                        frontend: "https://github.com/MarcGravel/Tweeter",
                        backend: "https://github.com/MarcGravel/TweeterBackendApi",
                        skills: "JavaScript, Vue.js, HTML, CSS, SASS, Python, Flask, MariaDB, SQL, Apache, Node.js, PM2",
                        additional: "Please feel free to sign up and check out the site. Alternatively, you would like login credentials for an existing account, please contact me directly.",
                    },
                    kneadPizza: {
                        name: "Knead Pizza",
                        color: "#8e8268",
                        type: "- Pizza restaurant",
                        buildDate: "July 2021",
                        url: "https://kneadpizza.ga",
                        img: "kneadpizzaScreen.png",
                        description: "Knead Pizza is a mock website for a hypothetical pizza restaurant. This is a static website and is created with pure CSS/SASS and HTML only. It displays information about the restaurant, its menu, an about page, and contact details.",
                        frontend: "https://github.com/MarcGravel/kneadPizza",
                        skills: "HTML, CSS, SASS, Apache",
                    },
                    thisSite: {
                        name: "This website",
                        color: "#656779",
                        type: "- Portfolio",
                        buildDate: "Nov 2021",
                        img: "portfolioScreen.png",
                        description: "If you would like to see the code for this website, please click the link below",
                        frontend: "https://github.com/MarcGravel/M-Portfolio",
                        skills: "JavaScript, Vue.js, HTML, CSS, SASS, Apache, Node.js",
                    },
                    comingSoon: {
                        name: "Coming Soon",
                        color: "#aaa0a0",
                        img: "comingSoon.jpg",
                    },
                }
            }
        }
    }
</script>

<style lang="scss" scoped>
    #project-section {
        width: 100vw;
        height: fit-content;
        background-color: rgba(170, 160, 160, 0.5);
        display: grid;
        align-items: center;
        justify-items: center;

        #project-container {
            width: 90vw;
            display: grid;
            margin-top: 3vh;
            margin-bottom: 3vh;

            h1 {
                margin-bottom: 3vh;
                color: whitesmoke;
                text-align: center;
                font-size: 2.5em;
            }

            #git-link {
                justify-self: center;
            }
        }
    }

    @media screen and (min-width: 700px) {
        #project-section {

            #project-container {
                grid-template-columns: 50% 50%;
                grid-template-rows: auto;
                grid-row-gap: 5vh;

                #proj-title {
                    grid-column: 1 / 3;
                }

                .project-items {
                    margin-left: 1vw;
                    margin-right: 1vw;
                }

                #git-link {
                    grid-column: 1 / 3;
                }
            }
        }
    }

    @media screen and (min-width: 1200px) {
        #project-section {

            #project-container {
                grid-template-columns: 33% 33% 33%;
                width: 80%;

                #proj-title {
                    grid-column: 1 / 4;
                }

                #git-link {
                    grid-column: 1 / 4;
                }
            }
        }
    }
</style>