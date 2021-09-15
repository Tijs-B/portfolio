<template>
    <div id="app">
        <TypedTitle title="Tijs Bergmans"/>
        <p>I am a Software Engineer, currently looking for an opportunity to challenge myself.
            I'm interested in Software Engineering, Software Security and Artificial Intelligence.</p>
        <h2>Contact me!</h2>
        <div class="contact-links">
            <div class="contact">
                <span><a href="mailto:tijs.be@gmail.com">tijs.be@gmail.com</a></span>
                <span><a href="https://github.com/Tijs-B" target="_blank">GitHub</a></span>
                <span><a href="https://www.linkedin.com/in/tijs-bergmans/" target="_blank">LinkedIn</a></span>
                <span><a href="/CV-Tijs-Bergmans.pdf" download>Resume</a></span>
            </div>
        </div>
    </div>
</template>

<script>
    import TypedTitle from "./components/TypedTitle";

    export default {
        name: 'App',
        components: {
            TypedTitle,
        }
    }
</script>

<style lang="scss">
    @import 'assets/style/_variables.scss';

    #app {
        font-family: "Open Sans", sans-serif;
        width: 1000px;
        max-width: 80vw;
        margin: 80px auto 0 auto;
        color: $primary-color;
    }

    body {
        background-color: $background-color;
    }

    p {
        font-size: 1.3em;
        line-height: 40px;
    }

    h2 {
        font-family: Monaco, Consolas, Lucida, Console, monospace;
        color: $accent-color;
        margin-top: 60px;
    }

    .contact-links {
        a {
            color: $primary-color;
            text-decoration: none;
            font-size: 1.3em;
            line-height: 40px;
        }
        span:not(span:last-child)::after {
            content: "||";
            margin: 0 15px;
            font-size: 1.3em;
            line-height: 40px;
        }
    }


    @media (max-width: 650px) {
        .contact-links span {
            width: 100%;
            display: block;
            text-align: center;

            &::after {
                display: none;
            }
        }
    }
</style>
