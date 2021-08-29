<template>
    <div class="products__product">
        <a :href="url">
            <div class="products__product--overlay"></div>
            <img
                loading="lazy"
                :src="require('../assets/' + image)"
                alt="product"
            />
            <p>{{ name }}</p>
        </a>
    </div>
</template>

<script>
export default {
    props: ['name', 'url', 'image'],
}
</script>
