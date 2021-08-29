<template>
    <div class="side-bar">
        <img
            loading="lazy"
            src="@/assets/key_side_banner_vafes.jpg"
            alt="thumbnail"
        />
        <img
            loading="lazy"
            src="@/assets/key_side_banner_primadoll.jpg"
            alt="thumbnail"
        />
        <img
            loading="lazy"
            src="@/assets/key_side_banner_kinenove.jpg"
            alt="thumbnail"
        />
        <img
            loading="lazy"
            src="@/assets/key_side_banner_sprb.jpg"
            alt="thumbnail"
        />
        <div class="twitter">
            <a href="https://twitter.com/key_official"><h2>Twitter</h2></a>
            <a
                class="twitter-timeline"
                data-width="300"
                data-height="500"
                href="https://twitter.com/key_official?ref_src=twsrc%5Etfw"
                >Tweets by Key_Official</a
            >
        </div>
    </div>
</template>

<style lang="scss" scoped>
.side-bar {
    width: 30em;
    margin-top: 2.5rem;
    img {
        width: 100%;
        border-radius: 1rem;
        border: 2px solid white;
        margin-bottom: 5rem;
    }
    @media (max-width: 1200px) {
        width: 100%;
        display: grid;
        gap: 1rem;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    }
    @media (max-width: 800px) {
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    }
    .twitter {
        a {
            text-decoration: none;
        }
        h2 {
            cursor: pointer;
            max-width: 30rem;
            text-align: center;
            background: var(--color-primary);
            color: white;
            padding: 1.2rem 2rem;
            margin-bottom: 1rem;
            border-radius: 2rem;
        }
    }
}
</style>
