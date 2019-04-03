<template>
</template>

<script>
    export default {
        name: "Tappable",
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

<style scoped>

</style>