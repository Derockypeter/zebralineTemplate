<template>
    <div class="absolute top-90">
        <div class="container">
            <div class="row" @click="showProductEditor">
                <div class="flex justify-between items-center px-4">
                    <h3>Featured Products</h3>
                    <a href="" class="learnmore">
                        <div>View All</div>
                        <div><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 2048 2048"><path d="M6.125 1088h1797.89l-402.976 403 89.994 90L2048 1024l-556.966-557-89.994 90 402.976 403H6.125v128z"></path></svg></div>
                    </a>
                </div>
                <div class="col s6 l3 m4" v-for="(product, index) in seededProducts" :key="index">
                    <div class="card">
                        <router-link :to="{ name: 'product-details', params: { product_name: product.title } }">
                            <img class="responsive-img image" width="400" height="400"
                                :src="product.images[0].url" alt="" loading="lazy"
                            />
                            <div class="astra-shop-summary-wrap">
                                <a
                                    href="https://websitedemos.net/office-furniture-store-04/product/ecoair-plant-on-brass/"
                                    class="ast-loop-product__link"
                                    ><h2 class="product__title">
                                        {{ product.title }}
                                    </h2></a
                                >
                                <span class="price"
                                    ><span class="amount"
                                        ><bdi
                                            ><span
                                                class="currencySymbol"
                                                >$</span
                                            >{{ product.curPrice }}</bdi
                                        ></span
                                    ></span
                                >
                                <div class="star-rating">
                                    <i class="fa-regular fa-star"></i>
                                    <i class="fa-regular fa-star"></i>
                                    <i class="fa-regular fa-star"></i>
                                    <i class="fa-regular fa-star"></i>
                                    <i class="fa-regular fa-star"></i>
                                </div>
                            </div>
                        </router-link>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
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
		}
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
							url: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2021/03/sports-shoe3-768x768.jpg",
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
			this.$emit('showProductEditor', true);
		}
	},
	mounted() {
		if (this.products.length > 0) {
			this.seededProducts = this.products;
		}
	},
	props: {
		products: Array,
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
  	}
}
</script>
<style scoped>
    .px-4 {
        padding: 4vh 0;
    }
    .flex {
        display: flex;
    }
    .justify-between {
        justify-content: space-between;
    }
    .items-center {
        align-items: center;
    }
    .absolute {
        position: absolute;
        width: 100%;
    }
    .top-90 {
        top: 180vh;
    }
    .image {
        width: 285px;
        height: 285px;
    }
    h3 {
        font-family: 'Lexend',sans-serif;
        font-weight: 600;
        font-size: 1.75rem;
        color: #26222f;
        line-height: 1.2em;
        margin: 0;
    }
    .learnmore {
        font-weight: 600;
        line-height: 1em;
        background-color: #00000000;
        border-style: solid;
        border-width: 0px 0px 1px 0px;
        border-radius: 0px 0px 0px 0px;
        padding: 0px 0px 4px 0px;
        display: inline-flex;
        color: #26222F;
        border-color: var(--primary-color);
        gap: 2vh;
    }
    .learnmore svg {
        fill: #26222F;
        width: 1.25rem;
    }
    .learnmore:hover {
        border-color: #26222F;
    }
    .product__title {
        font-size: 1em;
        margin-bottom: 0.5em;
        font-family: 'Lexend',sans-serif;
        line-height: 1.25em;
        color: #26222F;
        font-weight: 600;
    }
    .card {
        box-shadow: none;
    }
    .amount {
        line-height: 1.3;
        margin-bottom: 0;
        font-weight: 700;
        margin-bottom: 0.5em;
        font-size: .9em;
    }
    .astra-shop-summary-wrap {
        padding: 1vh 2vh;
    }
    .fa-star {
        color: #8b8698;
        font-size: .875rem;
    }
    @media only screen and (min-width: 1024px) {
        .top-90 {
            top: 290vh;
        }
        .image {
            width: 221px;
            height: 221px;
        }
        .container {
            width: 95%;
        }
    }
    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        .container {
            width: 95%;
        }
    }
    @media only screen and (max-width: 767px) {
        .top-90 {
            top: 165vh;
        }
        .image {
            width: 158px;
            height: 158px;
        }
        .product__title {
            margin-top: 0;
        }
    }
</style>