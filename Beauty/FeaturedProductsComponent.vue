<template>
    <div>
        <h6 class="title">Best Selling Products</h6>

        <div class="row rows">
            <div class="col s3 prod-all">
                <div class="selling-images">
                    <img
                        src="https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2018/06/coffee-asorted-600x600.jpg"
                        alt="images"
                        class="prod-img responsive-img"
                    />
                </div>

                <div class="image-description">
                    <p class="img-title">Groceries</p>
                    <h4 class="img-main">Assorted Coffee</h4>
                    <div class="rating">
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                    </div>
                    <p class="price">$35.00</p>
                </div>
            </div>

            <div class="col s3 prod-all">
                <div class="selling-images">
                    <img
                        src="https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2018/06/sanitizer-600x600.jpg"
                        alt="images"
                        class="prod-img"
                    />
                </div>

                <div class="image-description">
                    <p class="img-title">Groceries</p>
                    <h4 class="img-main">Assorted Coffee</h4>
                    <div class="rating">
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                    </div>
                    <p class="price">$35.00</p>
                </div>
            </div>

            <div class="col s3 prod-all">
                <div class="selling-images">
                    <img
                        src="https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2018/06/red-chillies-600x600.jpg"
                        alt="images"
                        class="prod-img"
                    />
                </div>

                <div class="image-description">
                    <p class="img-title">Groceries</p>
                    <h4 class="img-main">Assorted Coffee</h4>
                    <div class="rating">
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                    </div>
                    <p class="price">$35.00</p>
                </div>
            </div>

            <div class="col s3 prod-all">
                <div class="selling-images">
                    <img
                        src="https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2018/06/edible-oil-600x600.jpg"
                        alt="images"
                        class="prod-img"
                    />
                </div>

                <div class="image-description">
                    <p class="img-title">Groceries</p>
                    <h4 class="img-main">Assorted Coffee</h4>
                    <div class="rating">
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                        <i class="fa-regular fa-star"></i>
                    </div>
                    <p class="price">$35.00</p>
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
        font-family: 'Merriweather', serif;
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
        font-family: 'Merriweather', serif;
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
                        title: "Yellow Shoes",
                        category: {
                            name: "Men",
                        },
                        oldPrice: "$150.00",
                        curPrice: "$120.00",
                        rating: 3,
                        images: [
                            {
                                url: "https://transvelo.github.io/electro-html/2.0/assets/img/212X200/img1.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Dark Blue Jeans",
                        category: {
                            name: "Men",
                        },
                        curPrice: "$150.00",
                        rating: 2,
                        images: [
                            {
                                url: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2017/12/product-m-jeans1-768x768.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Blue Denim Jeans",
                        category: {
                            name: "Men",
                        },
                        curPrice: "$150.00",
                        rating: 3,
                        images: [
                            {
                                url: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2017/12/product-w-jeans2-768x768.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Blue Denim Short",
                        category: {
                            name: "Men",
                        },
                        curPrice: "$130.00",
                        rating: 4,
                        images: [
                            {
                                url: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2017/12/product-w-jeans1-768x768.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Anchor Bracelet",
                        category: {
                            name: "Men",
                        },
                        curPrice: "$120.00",
                        rating: 5,
                        images: [
                            {
                                url: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2017/12/product-accessory2-768x768.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Boho Bangle Bracelet",
                        category: {
                            name: "Men",
                        },
                        curPrice: "$120.00",
                        rating: 4,
                        images: [
                            {
                                url: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2017/12/product-accessory1-768x768.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Yellow Shoes",
                        category: {
                            name: "Men",
                        },
                        curPrice: "$120.00",
                        rating: 2,
                        images: [
                            {
                                url: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2017/12/product-bag1-768x768.jpg",
                            },
                        ],

                        link: "#",
                    },
                    {
                        title: "Bright Red",
                        category: {
                            name: "Men",
                        },
                        curPrice: "$120.00",
                        rating: 3,
                        images: [
                            {
                                url: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2017/12/product-bag3-768x768.jpg",
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