<template>
    <div id="footer">
        <div id="foot-links">
            <a href="https://www.linkedin.com/in/marc-gravel-1208061ba/" target="_blank">LinkedIn</a>
            <p>&nbsp;-&nbsp;</p>
            <a href="https://github.com/MarcGravel" target="_blank">Github</a>
            <p>&nbsp;-&nbsp;</p>
            <a href="mailto:gravel.m@outlook.com" target="_blank">gravel.m@outlook.com</a>
        </div>
        <div id="copyright">
            <p>© 2021 - Web design by Marc Gravel</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "BottomFooter"
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

            a, p {
                display: inline-block;
                color: whitesmoke;
                text-decoration: none;
            }

            a:hover {
                text-decoration: underline;
            }
        }

        #copyright {
            color: whitesmoke;
            opacity: 0.7;
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
</style>