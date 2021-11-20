<template>
    <div id="contact-form">
        <div id="form">
            <h1>Let's work together.</h1>
            <p>
                Use the form below to contact me for a copy of my resume, job opportunities, or to discuss your project and work towards a quote.
                You can also e-mail me directly at <a href="mailto:gravel.m@outlook.com">gravel.m@outlook.com</a>
            </p>
            <form id="form-action" action="https://formsubmit.co/gravel.m@outlook.com" method="POST">
                <input type="text" name="name" placeholder="Name" required>
                <input type="email" name="email" placeholder="Email address" required>
                <input type="text" name="company" placeholder="Company (Optional)">
                <textarea name="content" placeholder="Enter your message here..." required></textarea>
                <input type="text" name="_honey" style="display:none">
                <input type="hidden" name="_captcha" value="false">
                <input type="hidden" name="_template" value="box">
                <v-btn
                    id="form-sumbit"
                    type="submit"
                    color="primary"
                    >
                    Send
                </v-btn>
            </form>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ContactForm",
        data() {
            return {
                name: '',
                email: '',
                company: '',
                content: '',
            }
        }
    }
</script>

<style lang="scss" scoped>
    #contact-form {
        height: fit-content;
        width: 100vw;
        display: grid;
        justify-items: center;

        #form {
            width: 90%;
            height: fit-content;
            margin: 5vh 0 5vh 0;
            padding: 2vh 2vw 2vh 2vw;
            background-color: rgba(90, 86, 86, 0.9);
            border-radius: 10px;
            color: whitesmoke;

            p, a {
                color: whitesmoke;
                opacity: 0.8;
            }

            #form-action {
                margin-top: 7%;
                display: grid;
                justify-items: center;

                input, textarea {
                    margin-bottom: 2vh;
                    width: 90%;
                    padding: 5px;
                    background-color: whitesmoke;
                    opacity: 0.9;
                    border-radius: 5px;
                }
                
                textarea {
                    height: 150px;
                }

                #form-sumbit {
                    display: block;
                    justify-self: end;
                    margin-right: 10%;
                }
            }
        }
    }

    @media screen and (min-width: 700px) {
        #contact-form {
            #form {
                width: 650px;

                h1 {
                    margin-bottom: 3vh;
                }

                #form-action {
                    margin-top: 3vh;
                }
            }
        }
    }

    @media screen and (min-width: 1100px) {
        #contact-form {
            #form {
                width: 900px;
                display: grid;

                p {
                    width: 70%;
                    justify-self: center;
                }

            }
        }
    }
</style>