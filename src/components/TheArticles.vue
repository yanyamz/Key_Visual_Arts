<template>
    <section class="articles">
        <div class="article">
            <div class="article__thumbnail">
                <img
                    loading="lazy"
                    src="@/assets/keyinfo0825_thum1.jpg"
                    alt="thumbnail"
                />
            </div>
            <div class="article__summary">
                <h4 class="article__date">08.24.2021</h4>
                <h4 class="article__title">
                    第6話「雪華文様（１１）」を公開。 迫る敵軍。鴉羽の願いは……? 
                    <a href="https://key.visualarts.gr.jp/primadoll/">https://key.visualarts.gr.jp/primadoll/</a> 
                </h4>
            </div>
        </div>
        <div class="article">
            <div class="article__thumbnail">
                <img
                    loading="lazy"
                    src="@/assets/main_image_loopers_1211.jpg"
                    alt="thumbnail"
                />
            </div>
            <div class="article__summary">
                <h4 class="article__date">02.05.2021</h4>
                <h4 class="article__title">
                    『LOOPERS』のダウンロード版が、本日より予約販売を開始いたしました。詳しい情報は下記リンク先をご覧ください。
                </h4>
            </div>
        </div>
        <div class="article">
            <div class="article__thumbnail">
                <img
                    loading="lazy"
                    src="@/assets/keyinfo210202_thum1.png"
                    alt="thumbnail"
                />
            </div>
            <div class="article__summary">
                <h4 class="article__date">02.03.2021</h4>
                <h4 class="article__title">
                    「プリマドール」公式サイトを更新しました！
                </h4>
            </div>
        </div>
        <div class="article">
            <div class="article__thumbnail">
                <img
                    loading="lazy"
                    src="@/assets/keyinfo210201_thum1.jpg"
                    alt="thumbnail"
                />
            </div>
            <div class="article__summary">
                <h4 class="article__date">1.25.2020</h4>
                <h4 class="article__title">
                    「LOOPERS」公式サイトにて、店舗特典情報を公開しました！
                </h4>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.article {
    border-radius: 2rem;
    margin: 2.5rem 0;
    display: flex;
    align-items: center;

    height: 20rem;
    &__thumbnail {
        display: block;
        max-width: 24rem;
        height: 100%;
        border-radius: 2rem;
        margin-right: 1rem;
        @media (max-width: 650px) {
            // display: none;
            margin-top: 0.5rem;
            max-width: 10rem;
            height: 100%;
            align-self: flex-start;
            border-radius: 1rem;
        }
        img {
            width: 100%;
            height: 100%;
            border-radius: inherit;
            object-fit: cover;
            object-position: center;
        }
    }
    &__summary {
        @media (min-width: 650px) {
            clip-path: polygon(
                100% 0,
                100% 100%,
                1.5% 100%,
                1.5% 71%,
                1.5% 61%,
                0 51%,
                1.5% 40%,
                1.5% 28%,
                1.5% 14%,
                1.5% 0
            );
            padding-left: 1.7rem;
        }

        height: 100%;
        max-width: 50rem;
        padding: 1rem;
        background: white;
        border-radius: 2rem;
    }
    &__date {
        margin: 0.5rem 0;
        background: #454552;
        width: 100%;
        padding: 0.5rem;
        border-radius: 1rem;
        color: white;
        font-size: 1.8rem;
        font-weight: 300;
    }
    &__title {
        font-size: 1.8rem;
        font-weight: 700;
    }
}
</style>
