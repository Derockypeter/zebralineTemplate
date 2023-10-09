<template>
    <div>
        <h6 class="title">Best Selling Products</h6>

        <div class="row rows">
            <div
                class="col s3 prod-all"
                v-for="(product, index) in seededProducts"
                :key="index"
            >
                <div class="selling-images">
                    <img
                        :src="product.images[0].url"
                        alt="images"
                        class="prod-img responsive-img"
                    />
                </div>

                <div class="image-description">
                    <p>{{ product.category.name }}</p>
                    <h4 class="img-main">
                        <router-link
                            :to="{
                                name: 'product-details',
                                params: { product_name: product.title },
                            }"
                            class="img-title"
                            >{{ product.title }}</router-link
                        >
                    </h4>
                    <div class="rating">
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                    </div>
                    <p class="price">${{ product.curPrice }}</p>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
    /* Best Selling Section */

    .prod-img {
        width: 100%;
    }

    .rows {
        padding: 8vw;
    }

    .image-description {
        display: block;
        text-align: center;
    }

    .img-title {
        margin-bottom: 0%;
        font-size: 100%;
        font-weight: 200;
    }

    .img-main {
        margin: 1vh;
        font-size: 100%;
        font-weight: 600;
        font-family: "Merriweather", serif;
    }

    .rating {
        font-weight: 100;
    }

    .price {
        font-weight: 500;
        margin-top: 0.55vw;
    }

    .title {
        text-align: center;
        margin-top: 4vw;
        font-size: 200%;
        font-family: "Merriweather", serif;
    }
    @media only screen and (min-width: 1024px) {
        .container {
            width: 85%;
        }
    }
</style>
<script>
    export default {
        computed: {
            displayedProducts() {
                if (this.products && this.products.length > 0) {
                    return this.products;
                } else if (this.seededProducts && this.seededProducts.length > 0) {
                    return this.seededProducts;
                } else {
                    return [];
                }
            },
        },
        data() {
            return {
                seededProducts: [
                    {
                        title: "Assorted Coffee",
                        category: {
                            name: "Groceries",
                        },
                        oldPrice: "$150.00",
                        curPrice: "$120.00",
                        rating: 3,
                        images: [
                            {
                                url: "https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2018/06/coffee-asorted-600x600.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Assorted Coffee",
                        category: {
                            name: "Groceries",
                        },
                        curPrice: "$150.00",
                        rating: 2,
                        images: [
                            {
                                url: "https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2018/06/edible-oil-600x600.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Assorted Coffee",
                        category: {
                            name: "Groceries",
                        },
                        curPrice: "$150.00",
                        rating: 3,
                        images: [
                            {
                                url: "https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2018/06/red-chillies-600x600.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Assorted Coffee",
                        category: {
                            name: "Groceries",
                        },
                        curPrice: "$130.00",
                        rating: 4,
                        images: [
                            {
                                url: "https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2018/06/sanitizer-600x600.jpg",
                            },
                        ],

                        link: "#",
                    },
                ],
            };
        },
        methods: {
            showProductEditor() {
                if (this.loggedIn) {
                    this.$emit("showProductEditor", true);
                }
            },
        },
        mounted() {
            if (this.products.length > 0) {
                this.seededProducts = this.products;
            }
        },
        props: {
            products: Array,
            loggedIn: Boolean,
        },
        watch: {
            products: {
                handler(newProducts) {
                    if (newProducts.length > 0) {
                        this.seededProducts = [...newProducts]; // Make a copy of the new products
                    }
                },
                deep: true, // Enable deep watching to detect changes within the array
            },
        },
    };
</script>