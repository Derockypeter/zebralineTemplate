<template>
     <div class="row row-prod">
        <div v-if="categories && categories.length > 0">
            <div class="col s12 l4 m4" v-for="(category, index) in categories.slice(0, 3)"  :key="index">
                <div class="card feat-prod">
                    <h6 class="feat-descrip">{{ category.name }}</h6>
                    <p class="feat-text">{{ !category.image ? seeder[index].description : category.description }}</p>
                    <router-link :to="{ name: 'product-search-category', params: { category_name: category.name ?? 'category' }, query: { additionalData: category.id ?? 'category_id' } }" class="card-btn">SHOP NOW<i class="fa-solid fa-arrow-right feat-arrow"></i></router-link>
                </div>
            </div>
        </div>
        <div v-else>
            <div class="col s12 l4 m4" v-for="(category, index) in seeder.slice(0, 3)"  :key="index">
                <div class="card feat-prod">
                    <h6 class="feat-descrip">{{ category.name }}</h6>
                    <p class="feat-text">{{ !category.image ? seeder[index].description : category.description }}</p>
                    <router-link :to="{ name: 'product-search-category', params: { category_name: category.name ?? 'category' }, query: { additionalData: category.id ?? 'category_id' } }" class="card-btn">SHOP NOW<i class="fa-solid fa-arrow-right feat-arrow"></i></router-link>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                seeder: [
                    {
                        name: "Farm Fresh Products",
                        description:
                            "Aliquam porta justo nibh, id laoreet sapien sodales vitae justo.",
                        image: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2018/12/women-fashion-free-img.jpg",
                    },
                    {
                        name: "Fresh Vegetables",
                        description:
                            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin ac dictum.",
                        image: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2018/12/men-fashion-free-img.jpg",
                    },
                    {
                        name: "Organic Legume",
                        description:
                            "Phasellus sed urna mattis, viverra libero sed, aliquam est.",
                        image: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2018/12/footwear-free-img.jpg",
                    },
                ],
            };
        },
		props:{
			categories: Array
		},
		watch: {
			categories(newVal) {
                if (newVal) {
                    newVal.forEach((category, i) => {
                    if (i < this.seeder.length) {
                        // Update existing seeder items
                        this.seeder[i].name = category.name;
                        this.seeder[i].image = category.image || this.seeder[i].image;
                        this.seeder[i].description = category.description || this.seeder[i].description;
                    } else {
                        // Create new seeder items if there are more categories
                        this.seeder.push({
                        name: category.name,
                        image: category.image || null,
                        description: category.description || null,
                        });
                    }
                    });
                }
            },
    	},
    };
</script>
<style scoped>
     /* Featured Product Styling */

     .feat-prod {
        background-image: url(https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2019/06/product11-free-img.jpg);
        background-position: bottom right;
        background-repeat: no-repeat;
        background-size: contain;
        width: 100%;
        padding: 40px 40px 160px;
        background-color: white;
    }

    .feat-prods {
        background-image: url(https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2019/06/product13-free-img.jpg);
        background-position: bottom right;
        background-repeat: no-repeat;
        background-size: contain;
        width: 100%;
        padding: 40px 40px 160px;
        background-color: white;
    }

    .feat-product {
        background-image: url(https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2019/06/product17-free-img.jpg);
        background-position: bottom right;
        background-repeat: no-repeat;
        background-size: contain;
        width: 100%;
        padding: 40px 40px 160px;
        background-color: white;
    }

    .row-prod {
        padding: 8vw;
        background-color: rgb(248, 246, 242);
    }

    .feat-descrip {
        text-align: center;
        font-family: "Merriweather", serif;
        font-weight: 700;
        font-size: 150%;
    }

    .feat-text {
        text-align: center;
        font-size: 100%;
        font-weight: 300;
        margin-top: 2vh;
        padding: 0%;
        vertical-align: baseline;
    }

    .card-btn {
        padding: 4%;
        width: 50%;
        margin-top: 2vh;
        background-color: var(--primary-color);
        border: 0px solid transparent;
        border-radius: 5%;
        color: white;
    }

    .feat-arrow {
        margin-left: 0.55vw;
    }
    @media only screen and (min-width: 1024px) {
        .container {
            width: 85%;
        }
    }
    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        .container {
            width: 90%;
        }
        .md-mt-3 {
            margin-bottom: 3vh;
        }
    }
    @media only screen and (max-width: 767px) {
        .sm-mt-3 {
            margin-top: 3vh;
        }
        .chevyRight {
            width: 2vh;
            height: 2vh;
        }
        .chevyRight i {
            font-size: .8rem;
        }
    }
</style>