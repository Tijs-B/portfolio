<template>
    <h1>>&nbsp;{{ currentTitle }}<span v-bind:class="{ blink: startAnimation }">&nbsp;</span></h1>
</template>

<script>
    export default {
        name: "TypedTitle",
        props: {
            title: String,
            typingSpeed: {
                type: Number,
                default: 80,
            },
            initialDelay: {
                type: Number,
                default: 800,
            }
        },
        data() {
            return {
                currentTitle: "",
                startAnimation: false,
            }
        },
        mounted() {
            let currTypeSpeed = 0;
            let str = '';
            this.title.split('').forEach(c => {
                currTypeSpeed += this.typingSpeed + (Math.random() * 80 - 40)
                if (c === ' ') {
                    currTypeSpeed += 60
                }
                setTimeout(() => {
                    str += c;
                    this.currentTitle = str;
                }, this.initialDelay + currTypeSpeed);
            });
            setTimeout(() => {
                this.startAnimation = true;
            }, this.initialDelay + currTypeSpeed);
        }
    }
</script>

<style scoped lang="scss">
    @import '../assets/style/_variables.scss';

    h1 {
        font-family: Monaco, Consolas, Lucida, Console, monospace;
        color: $accent-color;
        font-size: 60px;

        span {
            background-color: $accent-color;
        }
    }

    @font-face {
        font-family: 'Monaco';
        font-style: normal;
        font-weight: normal;
        src: local('Monaco'), url('../assets/fonts/Monaco.woff') format('woff');
    }

    .blink {
        animation: blink 1s 500ms step-start infinite;
    }

    @keyframes blink {
        50% {
            opacity: 0;
        }
    }
</style>