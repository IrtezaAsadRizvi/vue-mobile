<script>
    export default {
        name: "Styleable",
        props: {
            styles: {
                type: Object,
                default: () => {
                    return {
                    }
                },
            },
        },
        mounted() {
            try {
                this.applyStyle(this.$refs.component, this.styles)
            }
            catch (error) {
                console.trace(error);
            }
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