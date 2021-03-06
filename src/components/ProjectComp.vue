<template>
    <div id="project-section">
        <div id="project-container">
            <h1 id=proj-title>Projects</h1>
            <div v-for="project in allProjects" :key="project.name" class="project-items">
                <ProjectItem :project="project" />
            </div>
        </div>
        <div id="git-link-container">
            <GitLinkBtn />
        </div>
        <hr id="main-break">
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
                    cas: {
                        name: "Calgary Animal Save",
                        color: "#7a6a81",
                        type: "Non-profit animal rights organization",
                        buildDate: "Dec 2021 - March 2022",
                        url: "https://calgaryanimalsave.com",
                        img: "casScreen.png",
                        description: "I built this website from the ground up for a Calgary based animal-rights organization. The project included building the database, back-end API, and front-end. The clients main requirements were to have the ability to post/update/delete campaigns, merch, features, etc, on the site. I built a whole user/admin aspect to the app that can only be accessed with proper credentials. The most challenging part of building this website was ensuring the user input would properly render valid html/css on user submit of a textarea (including images). This project also includes a shop and donate section in which stripe was integrated into the application to provide secure and reliable payments. Finally, the amount of data and images on this website required a lot of time spent on SEO and performance optimization.",
                        skills: "API integration, SEO + deployment performance, JavaScript, Vue.js, HTML, CSS, SCSS, Python, Flask, MariaDB, SQL, Apache, Node.js, PM2",
                        additional: "The code is not public as this is a live real-world website. Please contact me for questions or a run-down on any aspect of this project.",
                    },
                    jobjug: {
                        name: "JobJug",
                        color: "#86b3d1",
                        type: "- Project Management",
                        buildDate: "Oct-Nov 2021",
                        url: "https://jobjug.ca",
                        img: "jobjugScreen.png",
                        description: "JobJug is a project management web application meant for internal use between employees, managers, and admins. For security purposes, there is no ability to sign up. You can contact me for login credentials. All new users are created within the logged in app by existing managers or admin. JobJug allows users to log in to their personal profile to get up-to-date info about the company's current and past projects. The site is also equipped with automatic invoicing and email services. JobJug is mobile, tablet, and desktop friendly.",
                        frontend: "https://github.com/MarcGravel/JobJug",
                        backend: "https://github.com/MarcGravel/JobJugBackendApi",
                        skills: "JavaScript, Vue.js, HTML, CSS, SCSS, Python, Flask, MariaDB, SQL, Apache, Node.js, PM2",
                        additional: "Please contact me directly for a temporary account to view and enjoy the site.",
                    },
                    tweeter: {
                        name: "Tweeter",
                        color: "#844d36",
                        type: "- Social Media",
                        buildDate: "Sep-Oct 2021",
                        url: "https://thetweeter.ga",
                        img: "tweeterScreen.png",
                        description: "Tweeter is a social media website based on existing social media services. Tweeter allows users to log-in/sign-up to their own personal profile. From there users are able to edit their profile and add their own personal touch, including photos and bios. Users can create new posts, comment on existing posts, follow other users, receive notifications, and more! To navigate the site, use the navigation bars or click on usernames, posts, images, notifications, or any button. Tweeter is mobile, tablet, and desktop friendly.",
                        frontend: "https://github.com/MarcGravel/Tweeter",
                        backend: "https://github.com/MarcGravel/TweeterBackendApi",
                        skills: "JavaScript, Vue.js, HTML, CSS, SCSS, Python, Flask, MariaDB, SQL, Apache, Node.js, PM2",
                        additional: "Please feel free to sign up and check out the site. Alternatively, if you would like login credentials for an existing account, please contact me directly.",
                    },
                    kneadPizza: {
                        name: "Knead Pizza",
                        color: "#8e8268",
                        type: "- Pizza restaurant",
                        buildDate: "July 2021",
                        url: "https://kneadpizza.ga",
                        img: "kneadpizzaScreen.png",
                        description: "Knead Pizza is a mock website for a pizza restaurant. This is a static website and is created with CSS/SASS and HTML only. It displays information about the restaurant, its menu, an about page, and contact details.",
                        frontend: "https://github.com/MarcGravel/kneadPizza",
                        skills: "HTML, CSS, SCSS, Apache",
                        additional: "No credentials required. This is a static website with only navigation interactivity."
                    },
                    thisSite: {
                        name: "This website",
                        color: "#656779",
                        type: "- Portfolio",
                        buildDate: "Nov 2021",
                        url: "https://marcgravel.dev",
                        img: "portfolioScreen.png",
                        description: "If you would like to see the code for this website, please click the link below",
                        frontend: "https://github.com/MarcGravel/M-Portfolio",
                        skills: "JavaScript, Vue.js, HTML, CSS, SCSS, Apache, Node.js",
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
        display: grid;
        align-items: center;
        justify-items: center;
        overflow: hidden;

        #project-container {
            width: 90vw;
            display: grid;
            margin-top: 2vh;
            margin-bottom: 3vh;

            h1 {
                margin-bottom: 1vh;
                color: #86b3d1;
                text-align: center;
                font-size: 2.5em;
                font-family: 'Proza Libre', sans-serif;
            }
        }

        #git-link-container {
            margin: 20px 0 100px 0;
        }

        #main-break {
            width: 60vw;
        }
    }

    @media screen and (min-width: 700px) {
        #project-section {

            #project-container {
                grid-template-columns: 50% 50%;
                grid-template-rows: auto;
                grid-row-gap: 5vh;

                h1 {
                    font-size: 3.5em;
                    margin-bottom: 0;
                }

                #proj-title {
                    grid-column: 1 / 3;
                }

                .project-items {
                    margin-left: 1vw;
                    margin-right: 1vw;
                    z-index: 9;
                }

                #git-link-container {
                    justify-self: center;
                    align-self: center;
                    display: grid;
                    width: 95%;
                    max-width: 500px;
                    height: 100%;
                    align-items: center;
                    justify-items: center;
                    background: rgb(0,0,0);
                    background: radial-gradient(circle, rgba(9,9,9,1) 0%, rgba(9,9,9,0) 150%);
                    border: 1px solid rgba(68, 68, 68, 0.753);
                    border-bottom-left-radius: 5px;
                    border-bottom-right-radius: 5px;
                    overflow: hidden;
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

                #git-link-container {
                    width: 92%;
                }
            }
        }
    }
</style>