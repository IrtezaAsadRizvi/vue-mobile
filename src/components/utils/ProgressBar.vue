<template>
    <progress class="progress-linear"
              ref="component"></progress>
</template>

<script>
    import Styleable from '../mixins/Styleable';

    export default {
        name: "ProgressBar",
        mixins: [Styleable]
    }
</script>

<style lang="css" scoped>
    @import url('../../assets/global.css');

    .progress-linear {
        -webkit-appearance: none;
        -moz-appearance: none;
        appearance: none;
        border: none;
        height: 0.25em;
        color: var(--color_blue);
        background-color: var(--color_light_sky_blue);
        font-size: var(--font_size_regular);
        width: 100%;
    }

    .progress-linear::-webkit-progress-bar {
        background-color: transparent;
    }

    /* Determinate */
    .progress-linear::-webkit-progress-value {
        background-color: currentColor;
        transition: all 0.2s;
    }

    .progress-linear::-moz-progress-bar {
        background-color: currentColor;
        transition: all 0.2s;
    }

    .progress-linear::-ms-fill {
        border: none;
        background-color: currentColor;
        transition: all 0.2s;
    }

    /* Indeterminate */
    .progress-linear:indeterminate {
        background-size: 200% 100%;
        background-image: linear-gradient(to right, transparent 50%, currentColor 50%, currentColor 60%, transparent 60%, transparent 71.5%, currentColor 71.5%, currentColor 84%, transparent 84%);
        animation: progress-linear 2s infinite linear;
    }

    .progress-linear:indeterminate::-moz-progress-bar {
        background-color: transparent;
    }

    .progress-linear:indeterminate::-ms-fill {
        animation-name: none;
    }

    @keyframes progress-linear {
        0% {
            background-size: 200% 100%;
            background-position: left -31.25% top 0%;
        }
        50% {
            background-size: 800% 100%;
            background-position: left -49% top 0%;
        }
        100% {
            background-size: 400% 100%;
            background-position: left -102% top 0%;
        }
    }

</style>