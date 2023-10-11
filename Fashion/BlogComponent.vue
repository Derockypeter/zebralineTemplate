<template>
    <div>
        <div class="container" @click="showBlogEditor">
            <div class="row">
                <h1 class="centerAlign center">Blogs</h1>
                <div class="col s12 l3 m4 mb-4" v-for="blog in blogSeeder" :key="blog">
                    <img
                        src="https://risingtheme.com/html/demo-suruchi-v1/suruchi/assets/img/blog/blog4.png"
                        alt="girls"
                        class="responsive-img"
                    />
                    <p class="blog-description">{{ blog.title }}</p>
                    <h6 class="blog_description">
                        {{ blog.body.slice(0, 31) }}, <br />
                       {{ blog.category.name }}
                    </h6>

                    <button class="btn btn-blog waves waves-effect">
                        Read more
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
    .customer-title {
        text-align: center;
        margin-top: 2vh;
        margin-bottom: 15vh;
        font-size: 200%;
        font-family: "Merriweather", serif;
    }
    .mb-4 {
        margin-bottom: 4vh;
    }
    button.btn {
        background-color: var(--primary-color);
        box-shadow: none;
        color: #fff;
    }
    button.btn:hover {
        background-color: #fff;
        border: 1px solid var(--primary-color);
        color: var(--primary-color);
    }
</style>
<script>
    export default {
        data() {
            return {
                blogSeeder: [
                    {
                        url: "https://risingtheme.com/html/demo-suruchi-v1/suruchi/assets/img/blog/blog4.png",
                        category_id: 1,
                        category: {
                            name: "Women",
                        },
                        created_at: "2023-09-28T04:41:10.000000Z",
                        body: "Fashiion Trends in 2021 Styles, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut elit tellus, luctus nec ullamcorper mattis, pulvinar dapibus leo"
                    },
                    {
                        url: "https://risingtheme.com/html/demo-suruchi-v1/suruchi/assets/img/blog/blog3.png",
                        category_id: 1,
                        category: {
                            name: "Men",
                        },
                        created_at: "2023-09-28T04:41:10.000000Z",
                        body: "Fashiion Trends in 2021 Styles, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut elit tellus, luctus nec ullamcorper mattis, pulvinar dapibus leo"
                    },
                    {
                        url: "https://risingtheme.com/html/demo-suruchi-v1/suruchi/assets/img/blog/blog2.png",
                        category_id: 1,
                        category: {
                            name: "Kids",
                        },
                        created_at: "2023-09-28T04:41:10.000000Z",
                        body: "Fashiion Trends in 2021 Styles, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut elit tellus, luctus nec ullamcorper mattis, pulvinar dapibus leo"
                    },
                    {
                        url: "https://risingtheme.com/html/demo-suruchi-v1/suruchi/assets/img/blog/blog1.png",
                        category_id: 1,
                        category: {
                            name: "Accessories",
                        },
                        created_at: "2023-09-28T04:41:10.000000Z",
                        body: "Fashiion Trends in 2021 Styles, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut elit tellus, luctus nec ullamcorper mattis, pulvinar dapibus leo"
                    }
                ]
            }
        },
        methods: {
            showBlogEditor() {

            }
        },
        props: {
            blog: Array,
            loggedIn: Boolean
        },
        watch: {
            blog(newVal) {
                if (newVal.length > 0) {
                    this.blogSeeder = newVal;
                }
            }
        }
    };
</script>