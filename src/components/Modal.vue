<template>
    <div v-if="modalOpen" class="modal">
        <div @click="modalOpen = false" class="overlay"></div>
        <div class="container">
            <p>
                This website is a clone from the original
                <a href="https://key.visualarts.gr.jp/">here</a> my goal for
                this project was to get some experience by trying to replicate
                the design of a webpage. This is by no means the official site,
                I just wanted to make it exactly like the original.
            </p>
            <button @click="modalOpen = false">Exit</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            modalOpen: true,
        }
    },
}
</script>

<style lang="scss" scoped>
.overlay {
    z-index: 20500;
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
}

button {
    cursor: pointer;
    margin-top: 1rem;
    font-size: 1.8rem;
    padding: 0.5rem;
    border: none;
    color: white;
    border-radius: 0.5rem;
    background: var(--color-primary);
    &:hover {
        background: white;
        color: var(--color-primary);
        border-color: var(--color-primary);
        border: solid 0.1rem;
    }
}
.container {
    z-index: 30000;
    display: flex;
    flex-direction: column;
    justify-content: center;

    background: white;
    border-radius: 1rem;
    padding: 2rem;
    max-width: 50rem;
    font-size: 1.4rem;
    letter-spacing: 0.2rem;
    line-height: 2rem;
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1),
        0 4px 6px -2px rgba(0, 0, 0, 0.05);
}
.modal {
    z-index: 20000;
    position: fixed;
    background: rgba(0, 0, 0, 0.6);
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
