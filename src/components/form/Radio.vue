<template>
    <label class="pure-material-radio" ref="component">
        <input type="radio" name="group">
        <span><slot></slot></span>
    </label>
</template>

<script>
    export default {
        name: "Radio"
    }
</script>

<style scoped>
    .pure-material-radio {
        z-index: 0;
        position: relative;
        display: inline-block;
        color: var(--color_blue);
        font-size: 16px;
        line-height: 1.5;
    }

    /* Input */
    .pure-material-radio > input {
        appearance: none;
        -moz-appearance: none;
        -webkit-appearance: none;
        z-index: -1;
        position: absolute;
        left: -10px;
        top: -8px;
        display: block;
        margin: 0;
        border-radius: 50%;
        width: 40px;
        height: 40px;
        background-color: var(--color_black);
        outline: none;
        opacity: 0;
        transform: scale(1);
        pointer-events: none;
        transition: opacity 0.3s, transform 0.2s;
    }

    /* Span */
    .pure-material-radio > span {
        display: inline-block;
        width: 100%;
        cursor: pointer;
    }

    /* Circle */
    .pure-material-radio > span::before {
        content: "";
        display: inline-block;
        box-sizing: border-box;
        margin: 2px 10px 2px 0;
        border: solid 2px; /* Safari */
        border-color: var(--color_blue);
        border-radius: 50%;
        width: 20px;
        height: 20px;
        vertical-align: top;
        transition: border-color 0.2s;
    }

    /* Check */
    .pure-material-radio > span::after {
        content: "";
        display: block;
        position: absolute;
        top: 2px;
        left: 0;
        border-radius: 50%;
        width: 10px;
        height: 10px;
        background-color: var(--color_blue);
        transform: translate(5px, 5px) scale(0);
        transition: transform 0.2s;
    }

    /* Checked */
    .pure-material-radio > input:checked {
        background-color: var(--color_blue);
    }

    .pure-material-radio > input:checked + span::before {
        border-color: var(--color_blue);
    }

    .pure-material-radio > input:checked + span::after {
        transform: translate(5px, 5px) scale(1);
    }

    /* Hover, Focus */
    .pure-material-radio:hover > input {
        opacity: 0.04;
    }

    .pure-material-radio > input:focus {
        opacity: 0.12;
    }

    .pure-material-radio:hover > input:focus {
        opacity: 0.16;
    }

    /* Active */
    .pure-material-radio > input:active {
        opacity: 1;
        transform: scale(0);
        transition: transform 0s, opacity 0s;
    }

    .pure-material-radio > input:active + span::before {
        border-color: var(--color_blue);
    }

    /* Disabled */
    .pure-material-radio > input:disabled {
        opacity: 0;
    }

    .pure-material-radio > input:disabled + span {
        color: var(--color_blue);
        cursor: initial;
    }

    .pure-material-radio > input:disabled + span::before {
        border-color: currentColor;
    }

    .pure-material-radio > input:disabled + span::after {
        background-color: currentColor;
    }

</style>