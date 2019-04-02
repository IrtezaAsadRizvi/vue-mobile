<template>
    <button class="button"
            ref="component"
            @click="handleClick($event)">
        <slot></slot>
    </button>
</template>

<script>
    import Styleable from '../base/Styleable';

    export default {
        name: "Button",
        extends: Styleable,
        props: {
            styles: {
                type: Object,
                default: () => {
                    return {
                        color: '#212121',
                        backgroundColor: 'transparent',
                        fontSize: '16px'
                    }
                },
            },
        },
        methods: {
            handleClick(e) {
                this.$emit('click');
                this.createRipple(e)
            },
            createRipple (e) {
                var circle = document.createElement('div');

                var d = Math.max(e.target.clientWidth, e.target.clientHeight);

                // adding circle
                circle.style.width = circle.style.height = d + 'px';

                var rect = e.target.getBoundingClientRect();
                circle.style.left = e.clientX - rect.left -d/2 + 'px';
                circle.style.top = e.clientY - rect.top - d/2 + 'px';

                circle.classList.add('ripple');

                // styling circle
                circle.style.position = 'absolute';
                circle.style.borderRadius = '50%';
                circle.style.backgroundColor = 'rgba(0, 0, 0, 0.3)';
                circle.style.animation = 'ripple 0.6s linear';
                circle.style.transform = 'scale(0)';

                e.target.appendChild(circle);
            },
        }
    }
</script>

<style lang="css" scoped>
    @import url('../../assets/global.css');

    .button {
        padding: var(--padding_side);
        border: 0;
        outline: 0;
        color: white;
        text-transform: uppercase;
        border-radius: var(--border_radius_standard);
        box-shadow: 0 3px 1px -2px rgba(0,0,0,.2), 0 2px 2px 0 rgba(0,0,0,.14), 0 1px 5px 0 rgba(0,0,0,.12);
        transition: box-shadow 280ms cubic-bezier(.4,0,.2,1);

        overflow: hidden;
        position: relative;
    }
</style>