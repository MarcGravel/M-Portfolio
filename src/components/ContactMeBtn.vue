<template>
    <div id="contact-btn">
        <v-btn
            id="the-btn"
            @click="goToForm()"
            >
            <v-icon>chat_bubble_outline</v-icon>
            Contact me
        </v-btn>
    </div>
</template>

<script>
    export default {
        name: "ContactMeBtn",
        methods: {
            goToForm() {
                document.getElementById("contact-form").scrollIntoView();
            }
        }
    }
</script>

<style lang="scss" scoped>
    #contact-btn {
        position: fixed;
        top: 93vh;
        left: 100vw;
        z-index: 50;

        #the-btn {
            width: 150px;
            position: relative;
            right: 170px;
            background-color: #e91e63;
            color: whitesmoke;
            font-weight: bold;
            box-shadow: 
                0 0 1.5em 0.2em #e91e63,
                inset 0 0 0.7em 0 #86b3d1;
        }
    }

    @media screen and (min-width: 700px) {
        #contact-btn {

            #the-btn {
                right: 190px;
            }
        }
    }
</style>