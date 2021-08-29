<template>
    <i
        @click="scrollToTop"
        class="fa fa-arrow-up"
        aria-hidden="true"
        ref="scrollBtn"
    ></i>
</template>

<script>
export default {
    mounted() {
        window.onscroll = () => {
            if (
                document.body.scrollTop > 50 ||
                document.documentElement.scrollTop > 50
            ) {
                this.$refs.scrollBtn.style.display = 'block'
            } else {
                this.$refs.scrollBtn.style.display = 'none'
            }
        }
    },
    methods: {
        scrollToTop() {
            document.body.scrollTop = 0 // For Safari
            document.documentElement.scrollTop = 0 // For Chrome, Firefox, IE and Opera
        },
    },
}
</script>

<style lang="scss" scoped>
i {
    @media (min-width: 800px) {
        z-index: 15000;
        display: none;
        transition: all 0.3s;
        cursor: pointer;
        position: fixed;
        bottom: 5rem;
        right: 5rem;
        border-radius: 50%;
        padding: 1.2rem 1.4rem;
        font-size: 3rem;
        background: var(--color-primary);
        color: white;
        &:hover {
            opacity: 0.7;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1),
                0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
    }
}
</style>
