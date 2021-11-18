<template>
    <div id="project-section">
        <div id="project-container">
            <h1>Projects</h1>
            <div id="project-items">
                <h1>Placeholder</h1>
            </div>
            <GitLinkBtn id="git-link" />
        </div>
    </div>
</template>

<script>
import GitLinkBtn from '../components/GitLinkBtn.vue'

    export default {
        name: "ProjectComp",
        components: {
            GitLinkBtn,
        }
    }
</script>

<style lang="scss" scoped>
    #project-section {
        width: 100%;
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
</style>