<template>
    <div id="about-section">
        <div id="info-container">
            <h1>About me</h1>
            <img src="@/assets/nov21Mg.png" alt="Marc Gravel">
            <div id="about-content">
                <p>
                    Hello World! I'm Marc Gravel, a software developer based in Vancouver, B.C. I have a Full-stack Development Diploma from 
                    Innotech College where I graduated November 2021. I have been working professionally as a developer since then.
                </p>
                <p>
                    I crave knowledge and I love problem solving. I enjoy programming at either end of the tech stack whether it's creating well rounded and effective API's, 
                    optimizing database queries, or creating seamless and simple UI's for a fluid digital experience.
                </p>
                <p id="p-no-marg">
                    A bit about my past:
                </p> 
                <p>
                    I have always sought out growth and development throughout my professional and social life.
                    I worked my way up from a labor position to the Construction Manager for a large construction company in Alberta.
                    Over time, my curiosity got the best of me and I decided to try my hand at programming.
                    I haven't looked back since.
                </p>
                <p>
                    Outside of work, I compose and produce electronic music as my other main hobby.
                    I also enjoy snowboarding, travelling, and exploring new skills. 
                </p>
            </div>
        </div>
        <hr id="main-break">
    </div>  
</template>

<script>
    export default {
        name: "AboutComp",
    }
</script>

<style lang="scss" scoped>
    #about-section {
        width: 100%;
        height: fit-content;
        display: grid;
        align-items: center;
        justify-items: center;
        overflow: hidden;
        background: black;
        background: linear-gradient(rgba(255,255,255,0.0), black, black, rgba(255,255,255,0.0));
        
        #info-container {
            width: 90vw;
            display: grid;
            z-index: 2;
            margin-top: 3vh;
            margin-bottom: 3vh;

            h1 {
                margin-bottom: 3vh;
                color: #86b3d1;
                opacity: 0.9;
                text-align: center;
                font-size: 2.5em;
                font-family: 'Proza Libre', sans-serif;
            }

            img {
                justify-self: center;
                width: 80vw;
                max-width: 400px;
                margin-bottom: 3vh;
                border-radius: 2px;
            }

            #about-content {
                p {
                    font-family: Roboto, sans-serif;
                    margin-bottom: 2vh;
                    color: rgba(245, 245, 245, 0.856);
                    opacity: 0.9;
                    text-align: left;
                }

                #p-no-marg {
                    margin-bottom: 1vh;
                }
            }
        }

        #main-break {
            width: 60vw;
        }
    }

    @media screen and (min-width: 700px) {
        #about-section {
            #info-container {
                width: 70vw;

                h1 {
                    font-size: 3.5em;
                }
            }
        }
    }

    @media screen and (min-width: 1100px) {
        #about-section {
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
                width: 70vw;
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