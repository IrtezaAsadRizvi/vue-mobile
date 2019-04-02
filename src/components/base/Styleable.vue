<template>
    
</template>

<script>
    export default {
        name: "Styleable",
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
        mounted() {
            this.applyStyle(this.$refs.component, this.styles);
        },
        methods: {
            applyStyle(elem, styles) {
                for (var style in styles) {
                    if (styles.hasOwnProperty(style)) {
                        elem.style[style] = styles[style]
                    }
                }
            },
        }
    }
</script>

<style scoped>

</style>