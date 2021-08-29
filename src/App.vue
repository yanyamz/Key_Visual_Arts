<template>
    <Modal />
    <TheNavigation />
    <SlideShow />
    <div class="main-content">
        <TheArticles />
        <SideBar />
    </div>
    <TheProducts />
    <ScrollTop />
    <TheFooter />
</template>

<script>
import TheNavigation from '@/components/TheNavigation.vue'
import SlideShow from '@/components/SlideShow.vue'
import TheArticles from '@/components/TheArticles'
import SideBar from '@/components/SideBar'
import TheProducts from '@/components/TheProducts'
import TheFooter from '@/components/TheFooter'
import ScrollTop from '@/components/ScrollTop'
import Modal from '@/components/Modal'

export default {
    name: 'App',
    components: {
        Modal,
        TheNavigation,
        SlideShow,
        TheArticles,
        SideBar,
        TheProducts,
        TheFooter,
        ScrollTop,
    },
}
</script>

<style lang="scss">
:root {
    --color-primary: #58abda;
}

html {
    scroll-behavior: smooth;
    font-size: 62.5%;
    @media (max-width: 650px) {
        font-size: 50%;
    }
}

* {
    box-sizing: border-box;
    margin: 0;
}

body {
    font-family: Meiryo, sans-serif, monospace;
    background: #eaeaea;
    max-width: 1925px;
    margin: 0 auto;
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1),
        0 4px 6px -2px rgba(0, 0, 0, 0.05);
}

.main-content {
    padding: 5rem;
    width: 100%;
    display: flex;
    justify-content: center;
    & > div {
        margin: 0 5rem;
    }
    @media (max-width: 1200px) {
        flex-direction: column;
        align-items: center;
    }
    @media (max-width: 650px) {
        padding: 3rem;
    }
}

@keyframes fadeInFromTop {
    from {
        opacity: 0;
        transform: translateY(-5rem);
    }
    to {
        opacity: 1;
        transform: translateY(0rem);
    }
}

@keyframes fadeInFromRight {
    from {
        transform: translateX(200%);
    }
    to {
        transform: translateY(0rem);
    }
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}
</style>
