<template>
    <div>
        <a id="btn" href="https://github.com/MarcGravel" target="_blank">View my Github</a>
    </div>
</template>

<script>
    export default {
        name: "GitLinkBtn"
    }
</script>

<style lang="scss" scoped>
    #btn {
        color: whitesmoke;
        font-size: 1.5em;
        display: inline-block;
        text-decoration: none;
        font-weight: 900;
        border: 4px solid #86b3d1;
        padding: 0.25em 1em;
        border-radius: 10px;

        text-shadow: 
            0 0 0.1em rgba(245, 245, 245, 0.336),
            0 0 0.15em #86b3d1;
        
        box-shadow: 
            0 0 0.7em 0 #86b3d1,
            inset 0 0 0.7em 0 #86b3d1;

        position: relative;
    }

    #btn::before {
        pointer-events: none;
        content: '';
        position: absolute;
        background:#86b3d1;
        top: 120%;
        left: 0;
        width: 100%;
        height: 100%;

        transform: perspective(1em) rotateX(40deg) scale(1, 0.35);
        filter: blur(1.5em);
        opacity: 0.7;
    }

    #btn::after {
        content: '';
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        box-shadow: 0 0 1em 0.4em #86b3d1;
        opacity: 0;
        transition: opacity 200ms linear;
    }

    #btn:hover, #btn:focus {
        background: #86b3d1a2;
        color: rgb(0, 0, 0);
        text-shadow: none; 
    }

    #btn:hover::after, #btn:focus::after {
        opacity: 1;
    }

    #btn:hover::before, #btn:focus::before {
        opacity: 1;
    }
</style>