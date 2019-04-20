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
            activeStyles: {
                type: Object,
                default: () => {
                    return {
                    }
                },
            },
        },
        mounted() {
            let element = this.$refs.component;
            let element_style_regular;
            let self = this;

            try {
                // applying regular styles
                this.applyStyle(element, this.styles);
                element_style_regular = element.style;

                // applying on focus styles
                element.addEventListener("focus", () => {self.applyStyle(element, self.activeStyles)});
                element.addEventListener("blur", () => {self.applyStyle(element, element_style_regular)});
            }
            catch (error) {
                // eslint-disable-next-line
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