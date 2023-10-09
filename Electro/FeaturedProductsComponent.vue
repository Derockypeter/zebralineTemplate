<template>
    <div class="grey lighten-3">
        <div class="container">
            <div class="row" @click="showProductEditor">
                <div class="col s12">
                    <ul class="tabs">
                        <li class="tab col s3">
                            <a href="#test1 active">Best Deals</a>
                        </li>
                        <li class="tab col s3">
                            <a class="" href="#test2">TV & Video</a>
                        </li>
                    </ul>
                </div>
                <div id="test1" class="col s12">
                    <div class="row">
                        <div
                            class="col s12 l2 m3"
                            v-for="(product, index) in seededProducts"
                            :key="index"
                        >
                            <div class="card">
                                <div class="card-content">
                                    <span class="categoryText">Speakers</span>

                                    <router-link :to="{ name: 'product-details', params: { product_name: product.title } }" class="blue-text">
                                        {{ product.title }}
                                    </router-link>
                                    <img
                                        :src="product.images[0].url"
                                        class="responsive-img"
                                    />
                                    <div class="flex justify-between">
                                        <p class="amount">${{ product.curPrice }}</p>
                                        <div class="hide-on-med-and-down">
                                            <a href="" class="cartContener"
                                                ><i
                                                    class="fa-solid fa-cart-arrow-down"
                                                ></i
                                            ></a>
                                        </div>
                                    </div>
                                    <div
                                        class="flex justify-between pt-2 links hide"
                                    >
                                        <a
                                            href=""
                                            class="flex items-center gap-1"
                                        >
                                            <i
                                                class="fa-solid fa-code-compare"
                                            ></i>
                                            <span>Compare</span>
                                        </a>
                                        <a
                                            href=""
                                            class="flex items-center gap-1"
                                        >
                                            <i class="fa-regular fa-heart"></i>
                                            <span>Add to Wishlist</span>
                                        </a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
    .tabs {
        background-color: #eeeeee;
    }

    .tabs .tab a {
        color: #343f49;
    }
    .tabs .tab a:hover,
    .tabs .tab a.active {
        background-color: transparent;
        color: #343f49;
        font-weight: 700;
    }
    .tabs .tab a:focus,
    .tabs .tab a:focus.active {
        background-color: transparent;
    }
    .card {
        box-shadow: none;
    }
    .card:hover {
        box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.14),
            0 3px 1px -2px rgba(0, 0, 0, 0.12), 0 1px 5px 0 rgba(0, 0, 0, 0.2);
    }
    .pt-2 {
        padding-top: 2vh;
    }
    .gap-1 {
        gap: 1vh;
    }
    .links a {
        color: #848484 !important;
        font-size: 0.81288rem;
    }
    .blue-text {
        font-size: 0.875rem;
        font-weight: 700;
    }
    .categoryText {
        font-size: 0.74987rem;
        color: #878787 !important;
    }
    .cartContener {
        width: 4vh;
        height: 4vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #fed700;
        border-radius: 100%;
        color: #fff;
    }
    .amount {
        color: #343f49;
        font-size: 1.25038rem;
        font-weight: 400;
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