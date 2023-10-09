<template>
    <div class="absolute top-90">
        <div class="container">
            <div v-if="categories && categories.length > 0">
                <div
                    class="row items-center md-flex lg-flex"
                    v-for="(category, index) in categories.slice(0, 3)"
                    :key="index"
                >
                    <div class="col s12 m6 l6">
                        <h6>{{ category.name }}</h6>
                        <p class="subtitle">
                            Smooth workflow at home with your own working space
                        </p>
                        <div class="divider"></div>
                        <p class="desc">
                            {{
                                !category.image
                                    ? seeder[index].description
                                    : category.description
                            }}
                        </p>
                        <a href="" class="learnmore">
                            <div>Learn More</div>
                            <div>
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    viewBox="0 0 2048 2048"
                                >
                                    <path
                                        d="M6.125 1088h1797.89l-402.976 403 89.994 90L2048 1024l-556.966-557-89.994 90 402.976 403H6.125v128z"
                                    ></path>
                                </svg>
                            </div>
                        </a>
                    </div>
                    <div class="col s12 m6 l6">
                        <img
                            :src="category.image"
                            alt=""
                            class="responsive-img"
                        />
                    </div>
                </div>
            </div>
            <div v-else>
                <div
                    class="row items-center md-flex lg-flex"
                    v-for="(category, index) in seeder.slice(0, 3)"
                    :key="index"
                >
                    <div class="col s12 m6 l6">
                        <h6>{{ category.name }}</h6>
                        <p class="subtitle">
                            Smooth workflow at home with your own working space
                        </p>
                        <div class="divider"></div>
                        <p class="desc">
                            {{
                                !category.image
                                    ? seeder[index].description
                                    : category.description
                            }}
                        </p>
                        <a href="" class="learnmore">
                            <div>Learn More</div>
                            <div>
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    viewBox="0 0 2048 2048"
                                >
                                    <path
                                        d="M6.125 1088h1797.89l-402.976 403 89.994 90L2048 1024l-556.966-557-89.994 90 402.976 403H6.125v128z"
                                    ></path>
                                </svg>
                            </div>
                        </a>
                    </div>
                    <div class="col s12 m6 l6">
                        <img :src="category.image" alt="" class="responsive-img" />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
    .flex {
        display: flex;
    }
    .items-center {
        align-items: center;
    }
    .absolute {
        position: absolute;
        width: 100%;
    }
    .top-90 {
        top: 80vh;
    }
    h6 {
        text-transform: uppercase;
        letter-spacing: 2px;
        line-height: 1.25rem;
        font-size: 0.9333333333rem;
        font-weight: 600;
        color: #26222f;
        font-family: "Lexend", sans-serif;
    }
    .subtitle {
        font-size: 1.75rem;
        font-family: "Lexend", sans-serif;
        margin: 0;
        line-height: 1.25em;
        font-weight: 600;
    }
    .divider {
        width: 10%;
        margin: 3vh 0;
        background: #fbd84b;
        height: 2px;
    }
    .desc {
        color: #8b8698;
        font-family: "Inter", sans-serif;
        line-height: 1.6rem;
        font-size: 1rem;
        font-weight: 400;
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
        color: #26222f;
        border-color: #fbd84b;
        gap: 2vh;
    }
    .learnmore svg {
        fill: #26222f;
        width: 1.25rem;
    }
    .learnmore:hover {
        border-color: #26222f;
    }
    @media only screen and (min-width: 1024px) {
        .lg-flex {
            display: flex;
        }
    }
    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        .md-flex {
            display: flex;
        }
        .top-90 {
            top: 40vh;
        }
        .container {
            width: 95%;
        }
    }
    @media only screen and (max-width: 767px) {
        h6 {
            font-size: 0.8rem;
        }
        .learnmore {
            margin-bottom: 5vh;
        }
        .top-90 {
            top: 65vh;
        }
    }
</style>
<script>
    export default {
        data() {
            return {
                seeder: [
                    {
                        name: "Women Fashion",
                        description: `Et arcu eu ultricies pharetra, malesuada congue egestas
                                venenatis pellentesque vitae massa aliquet quis velit
                                elementum. Arcu erat turpis sed ullamcorper viverra amet,
                                vel laoreet massa eu consequat ultricies accumsan, a magna
                                morbi egestas augue proin sagittis, sit neque volutpat nisl
                                elit mattis aenean eget eget facilisis massa duis volutpat
                                purus diam nec at orci lacinia lectus id enim diam vivamus
                                euismod nibh venenatis.`,
                        image: "https://websitedemos.net/office-furniture-store-04/wp-content/uploads/sites/913/2021/07/furniture-store-home-office-intro-img.jpg",
                    },
                    {
                        name: "Men Fashion",
                        description: `Et arcu eu ultricies pharetra, malesuada congue egestas
                                venenatis pellentesque vitae massa aliquet quis velit
                                elementum. Arcu erat turpis sed ullamcorper viverra amet,
                                vel laoreet massa eu consequat ultricies accumsan, a magna
                                morbi egestas augue proin sagittis, sit neque volutpat nisl
                                elit mattis aenean eget eget facilisis massa duis volutpat
                                purus diam nec at orci lacinia lectus id enim diam vivamus
                                euismod nibh venenatis.`,
                        image: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2018/12/men-fashion-free-img.jpg",
                    },
                    {
                        name: "Accessories",
                        description: `Et arcu eu ultricies pharetra, malesuada congue egestas
                                venenatis pellentesque vitae massa aliquet quis velit
                                elementum. Arcu erat turpis sed ullamcorper viverra amet,
                                vel laoreet massa eu consequat ultricies accumsan, a magna
                                morbi egestas augue proin sagittis, sit neque volutpat nisl
                                elit mattis aenean eget eget facilisis massa duis volutpat
                                purus diam nec at orci lacinia lectus id enim diam vivamus
                                euismod nibh venenatis.`,
                        image: "https://websitedemos.net/brandstore-02/wp-content/uploads/sites/150/2018/12/footwear-free-img.jpg",
                    },
                ],
            };
        },
        props: {
            categories: Array,
        },
        watch: {
            categories(newVal) {
                if (newVal) {
                    newVal.forEach((category, i) => {
                        if (i < this.seeder.length) {
                            // Update existing seeder items
                            this.seeder[i].name = category.name;
                            this.seeder[i].image =
                                category.image || this.seeder[i].image;
                            this.seeder[i].description =
                                category.description || this.seeder[i].description;
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