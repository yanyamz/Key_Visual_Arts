<template>
    <div class="slideshow">
        <div class="slideshow__background">
            <img
                :src="require('../assets/' + images[currentImage])"
                alt="thumbnail"
            />
            <div class="slideshow__blur"></div>
        </div>
        <div class="slideshow__spotlight">
            <img
                :src="require('../assets/' + images[currentImage])"
                alt="thumbnail"
            />
        </div>
        <div class="slideshow__thumbnails">
            <div
                class="slideshow__thumbnail"
                :class="{ halfTransparent: thumbnail !== images[currentImage] }"
                v-for="thumbnail of thumbnailOrder"
                :key="thumbnail"
                @click="updateSpotlight(thumbnail)"
            >
                <img :src="require('../assets/' + thumbnail)" alt="thumbnail" />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    mounted() {
        this.changeSpotlight()
    },
    data() {
        return {
            currentImage: 0,
            images: [
                'main_image_planetarian_ue_4.jpg',
                'main_image_kamisama.jpg',
                'main_image_sprb_onsale.jpg',
                'main_image_3.jpg',
                'main_image_loopers_1211.jpg',
            ],
            thumbnailOrder: [
                'main_image_planetarian_ue_4.jpg',
                'main_image_kamisama.jpg',
                'main_image_sprb_onsale.jpg',
                'main_image_3.jpg',
                'main_image_loopers_1211.jpg',
            ],
        }
    },
    methods: {
        changeSpotlight() {
            setInterval(() => {
                this.moveRight()
                this.updateThumbnailOrder()
            }, 6000)
        },
        moveRight() {
            if (this.currentImage != this.images.length - 1) {
                this.currentImage++
            } else {
                this.currentImage = 0
            }
        },
        updateSpotlight(thumbnail) {
            this.currentImage = this.images.indexOf(thumbnail)
            this.updateThumbnailOrder()
        },
        updateThumbnailOrder() {
            let currentIndex = this.currentImage
            let updatedOrder = []
            const moveRight = () => {
                if (currentIndex != this.images.length - 1) {
                    currentIndex++
                } else {
                    currentIndex = 0
                }
            }
            for (let i = 0; i < this.images.length; i++) {
                updatedOrder[i] = this.images[currentIndex]
                moveRight()
            }
            const [a, b, c, d, e] = updatedOrder
            this.thumbnailOrder[0] = d
            this.thumbnailOrder[1] = e
            this.thumbnailOrder[2] = a
            this.thumbnailOrder[3] = b
            this.thumbnailOrder[4] = c
        },
    },
}
</script>

<style lang="scss">
.slideshow {
    position: relative;
    width: 100%;
    height: 58rem;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    @media (max-width: 1000px) {
        height: 37rem;
    }
    @media (max-width: 650px) {
        height: 30rem;
    }
    &__background {
        position: absolute;
        top: 0;
        width: 100%;
        height: 100%;
        img {
            position: absolute;
            width: 100%;
            height: 100%;
            object-position: center;
            object-fit: cover;
            filter: blur(15px);
        }
    }
    &__blur {
        position: absolute;
        width: 100%;
        height: 100%;
        background: rgba(255, 255, 255, 0.5);
    }
    &__spotlight {
        animation: fadeIn 3s ease-out forwards;
        z-index: 1000;
        width: 70%;
        height: 65%;
        border-radius: 2rem;
        @media (max-width: 650px) {
            width: 90%;
        }
        img {
            border: 4px solid white;
            width: 100%;
            height: 100%;
            object-position: center;
            object-fit: cover;
            border-radius: inherit;
        }
    }
    &__thumbnails {
        z-index: 1500;
        width: 100%;
        height: 11rem;
        display: flex;
        justify-content: space-around;
        @media (max-width: 1200px) {
            height: 9rem;
        }
        @media (max-width: 1000px) {
            height: 6rem;
        }
        @media (max-width: 650px) {
            display: none;
        }
    }
    &__thumbnail {
        cursor: pointer;
        width: 15%;
        height: 100%;
        border-radius: 2rem;
        transition: all 0.4s;
        &:hover {
            opacity: 1;
        }
        img {
            border: solid 2px white;
            width: 100%;
            height: 100%;
            border-radius: inherit;
            object-fit: cover;
            object-position: center;
        }
    }
}

.halfTransparent {
    opacity: 0.5;
}
</style>
