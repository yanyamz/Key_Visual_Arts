<template>
    <section class="products">
        <div class="products__header">
            <p>✢</p>
            <div class="line"></div>
            <h3 class="products__title">Products</h3>
            <div class="line"></div>
            <p>✢</p>
        </div>
        <div class="products__gallery">
            <TheProductsItem
                v-for="product in products"
                :key="product.name"
                :name="product.name"
                :url="product.url"
                :image="product.image"
            />
        </div>
    </section>
</template>

<script>
import TheProductsItem from '@/components/TheProducts_Item'

export default {
    components: {
        TheProductsItem,
    },
    data() {
        return {
            products: [
                {
                    name: 'Loopers',
                    url: 'https://key.visualarts.gr.jp/kinetic/loopers/',
                    image: 'product_image_loopers.jpg',
                },
                {
                    name: 'Kamisama Day',
                    url: 'https://kamisama-day.jp',
                    image: 'product_image_kamisama.jpg',
                },
                {
                    name: 'Summer Pockets REFLECTION BLUE',
                    url: 'https://key.visualarts.gr.jp/summer_rb/',
                    image: 'product_image_sprb.jpg',
                },
                {
                    name: 'Summer Pockets ',
                    url: 'https://key.visualarts.gr.jp/summer/',
                    image: 'product_image_sp.jpg',
                },
                {
                    name: 'Charlotte',
                    url: 'https://charlotte-anime.jp/',
                    image: 'product_image_charlotte.jpg',
                },
                {
                    name: 'Harmonia',
                    url: 'https://charlotte-anime.jp/',
                    image: 'product_image_harmonia.jpg',
                },
                {
                    name: 'Angel Beats',
                    url: 'https://key.visualarts.gr.jp/angelbeats/',
                    image: 'product_image_ab1st.jpg',
                },

                {
                    name: 'Kud Wafer',
                    url: 'https://key.visualarts.gr.jp/kudo/',
                    image: 'product_image_kudwaf.jpg',
                },
                {
                    name: 'ReWrite',
                    url: 'https://key.visualarts.gr.jp/rewrite/',
                    image: 'product_image_rewritehf.jpg',
                },
                {
                    name: 'Clannad',
                    url: 'https://key.visualarts.gr.jp/product/clannad/',
                    image: 'product_image_clannad.jpg',
                },
                {
                    name: 'Planetarian',
                    url: 'https://key.visualarts.gr.jp/product/planetarian/',
                    image: 'product_image_planetarian.jpg',
                },
                {
                    name: 'Air',
                    url: 'https://key.visualarts.gr.jp/product/air/',
                    image: 'product_image_air.jpg',
                },
                {
                    name: 'Kanon',
                    url: 'https://key.visualarts.gr.jp/product/kanon/',
                    image: 'product_image_kanon.jpg',
                },
            ],
        }
    },
}
</script>

<style lang="scss">
.line {
    width: 10rem;
    height: 0.2rem;
    background: white;
}
.products {
    width: 100%;
    height: 100%;
    padding: 5rem;

    background: #4e4e5c;
    @media (max-width: 800px) {
        padding: 2rem;
    }
    &__header {
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-bottom: 5rem;
        p {
            margin: 0 1rem;
            font-size: 2rem;
            color: white;
        }
    }
    &__title {
        margin: 0 2rem;
        font-size: 2.4rem;
        color: white;
    }
    &__gallery {
        width: 100%;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(30rem, 1fr));
        gap: 2rem;
        @media (max-width: 800px) {
            grid-template-columns: 1fr 1fr;
        }
    }
    &__product {
        position: relative;
        border-radius: 2rem;
        overflow: hidden;
        img {
            border-radius: inherit;
            width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: center;
        }
        p {
            animation: fadeInFromTop 0.4s ease-out forwards;
            animation-play-state: paused; /* but paused */
            font-weight: 200;
            display: none;
            opacity: 0;
            z-index: 5000;
            position: absolute;
            font-size: 2.4rem;
            color: white;
            top: 1rem;
            left: 0;
            width: 100%;
            text-align: center;
        }
        &:hover &--overlay {
            z-index: 4000;
            cursor: pointer;
            position: absolute;
            border-radius: inherit;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.2);
        }
        &:hover {
            img {
                filter: blur(5px);
            }
        }
        &:hover p {
            display: inline-block;
            animation-play-state: running; /* trigger on hover */
        }
    }
}
</style>
