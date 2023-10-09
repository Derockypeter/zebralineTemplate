<template>
    <div class="container" @click="showHeroEditor">
        <div class="hero">
            <div class="hero-img">
                <img
                    :src="imageUrlWithTimestamp"
                    alt="image"
                    class="hero-image"
                />
            </div>

            <div class="hero-text">
                <h6 class="hero-text-one">{{ heroSeeder[index].others }}</h6>
                <h2 class="hero-description">
                    {{ heroSeeder[index].description }}
                </h2>
                <p class="hero-description-text">.</p>
                <button class="hero-btn">
                    <i class="fa-solid fa-cart-shopping btn-hero"></i>SHOP NOW
                </button>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        computed: {
            imageUrlWithTimestamp() {
                // Append the timestamp as a query parameter to the image URL
                return `${this.heroSeeder[this.index].image}?t=${this.timestamp}`;
            },
        },
        data() {
            return {
                index: 0,
                heroSeeder: [
                    {
                        description:
                            "Join The Organic. Movement!Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut elit tellus, luctus nec ullamcorper mattis, pulvinar dapibus leo",
                        image: "https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2021/03/organic-products-hero.png",
                        others: "Best Quality Products",
                    },
                    {
                        description: "The new Standard",
                        image: "https://transvelo.github.io/electro-html/2.0/assets/img/416X420/img2.png",
                        others: "Under favorable smartwatches",
                    },
                    {
                        description: "The new Standard",
                        image: "https://transvelo.github.io/electro-html/2.0/assets/img/416X420/img3.png",
                        others: "Under favorable smartwatches",
                    },
                ],
            };
        },
        mounted() {
            this.initCarousel();
        },
        methods: {
            initCarousel() {
                document.addEventListener("DOMContentLoaded", () => {
                    let elem = document.getElementById("promo");
                    let instance = M.Carousel.init(elem, {
                        fullWidth: true,
                        indicators: true,
                    });

                    // Autoplay functionality
                    let autoplayInterval = 4500; // Delay between slide transitions in milliseconds
                    let autoplayInstance = setInterval(() => {
                        instance.next();
                    }, autoplayInterval);

                    // Pause autoplay on mouseover and resume on mouseout
                    elem.addEventListener("mouseenter", () => {
                        clearInterval(autoplayInstance);
                    });

                    elem.addEventListener("mouseleave", () => {
                        autoplayInstance = setInterval(() => {
                            instance.next();
                        }, autoplayInterval);
                    });

                    window.next = function () {
                        var el = document.querySelector(".carousel");
                        var l = M.Carousel.getInstance(el);
                        l.next(1);
                    };

                    //carousel previous function
                    window.prev = function () {
                        var el = document.querySelector(".carousel");
                        var l = M.Carousel.getInstance(el);
                        l.prev(1);
                    };
                });
            },
            showHeroEditor() {
                if (this.loggedIn) {
                    this.$emit("showHeroEditor", true);
                }
            },
        },
        props: {
            loggedIn: Boolean,
            hero: Object,
            timestamp: Number,
        },
        watch: {
            hero(newVal, oldVal) {
                if (Object.entries(newVal).length > 0) {
                    this.heroSeeder = newVal;
                    // this.heroSeeder.description = newVal.description ?? this.heroSeeder.description;
                    // this.heroSeeder.image = newVal.image ?? this.heroSeeder.image;
                    // this.heroSeeder.others = newVal.others ?? this.heroSeeder.others;
                }
            },
        },
    };
</script>
<style scoped>
    /* Hero Section Styling */

    .hero {
        /* width: 80%; */
        display: flex;
        justify-content: space-between;
        gap: 12%;
        align-items: center;
        padding-top: 4vw;
        font-family: "Merriweather", serif;
    }

    .container {
        margin-left: 2%;
        margin-right: 2%;
        font-family: "Merriweather", serif;
    }

    .hero-text-one {
        font-weight: 800;
    }

    .hero-description {
        font-weight: bold;
        font-size: 700;
        width: 100%;
    }

    .hero-description-text {
        font-size: 200;
        font-weight: 100;
        width: 200%;
        color: rgb(120, 119, 119);
    }

    .hero-btn {
        padding: 4%;
        width: 60%;
        border: 0px transparent;
        background-color: var(--primary-color);
        border-radius: 5%;
        color: white;
        margin-top: 5%;
    }

    .btn-hero {
        margin-right: 5%;
    }

    @media only screen and (max-width: 767px) {
        .hero-text-one {
            font-weight: 200;
            align-items: center;
            color: brown;
        }

        .hero-img {
            width: 20%;
        }

        .container {
            margin: 0%;
            font-family: "Merriweather", serif;
        }
    }

    @media only screen and (min-width: 1024px) {
        .carouselContainer {
            width: 50%;
        }
        .mt-10 {
            margin-top: 10vh;
        }
    }
    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        .carousel {
            height: 368px;
        }
        .heading {
            font-size: 2rem;
        }
        .desc {
            font-size: 1rem !important;
            font-family: "Poppins", sans-serif;
            width: 45vw;
        }
        .carouselContainer {
            width: 90%;
        }
    }
    @media only screen and (max-width: 767px) {
        .carousel {
            height: 300px;
        }
        .carouselContainer {
            padding: 2vh 0;
        }
        .heading {
            font-size: 1.75rem;
        }
        .desc {
            font-size: 1.125rem !important;
            width: 259px;
        }
        .startNowBtn {
            padding: 20px 20px;
        }
    }
</style>