<template>
    <div id="about-section">
        <div id="info-container">
            <h1>About me</h1>
            <img src="@/assets/placeholder.png" alt="Marc Gravel">
            <div id="about-content">
                <p>
                    Hello World! I'm Marc Gravel, a junior developer based in Vancouver, B.C. I have a Full-stack Development diploma from 
                    Innotech College where I graduated November 2021.
                </p>
                <p>
                    I crave knowledge and love problem solving. I enjoy programming at either end of the tech stack whether it's creating well rounded and effective API's, 
                    optimizing database queries, or creating seamless and simple UI's for a fluid digital experience.
                </p>
                <p id="p-no-marg">
                    A bit about my past:
                </p> 
                <p>
                    I have always sought out growth and development throughout my professional and social life.
                    I worked my way up from a labor position to a Construction Manager for a large construction company in Alberta.
                    Over time, my curiosity got the best of me and I decided to try my hand a programming
                    and I haven't looked back since. I first began my journey in August 2020 and programming has now turned into a life long passion and career.
                </p>
                <p>
                    Outside of work, I compose and produce electronic music as my other main hobby.
                    I also enjoy snowboarding, travelling, and learning new skills. 
                </p>
            </div>
        </div>
    </div>  
</template>

<script>
    export default {
        name: "About",
    }
</script>

<style lang="scss" scoped>
    #about-section {
        width: 95vw;
        min-height: 50vh;
        height: fit-content;
        background-color: #EAE7DC;
        display: grid;
        align-items: center;
        justify-items: center;
        
        #info-container {
            width: 90vw;
            display: grid;
            z-index: 2;
            margin-top: 3vh;
            margin-bottom: 3vh;

            h1 {
                margin-bottom: 3vh;
                color: #E85A4F;
                text-align: center;
                font-size: 2.5em;
            }

            img {
                justify-self: center;
                width: 80vw;
                max-width: 400px;
                margin-bottom: 3vh;
            }

            #about-content {
                p {
                    font-family: Roboto, sans-serif;
                    margin-bottom: 2vh;
                }

                #p-no-marg {
                    margin-bottom: 1vh;
                }
            }
        }
    }

    @media screen and (min-width: 700px) {
        #about-section {
            #info-container {
                width: 70vw;
            }
        }
    }

    @media screen and (min-width: 1100px) {
        #about-section {
            width: 90vw;
            min-height: 30vh;

            #info-container {
                width: 80vw;
                grid-template-columns: 50% 50%;
                grid-template-rows: 20% 80%;
                align-items: center;

                h1 {
                    grid-column: 1 / 3;
                    grid-row: 1;
                }
            }
        }
    }

    @media screen and (min-width: 1500px) {
        #about-section {

            #info-container {
                width: 60vw;
                grid-template-columns: 50% 50%;
                grid-template-rows: 20% 80%;

                h1 {
                    grid-column: 1 / 3;
                    grid-row: 1;
                }
            }
        }
    }
</style>