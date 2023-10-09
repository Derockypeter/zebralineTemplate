<template>
    <div>
        <nav class="nav">
            <div class="nav-wrapper">
                <a :href="loggedIn ? `#!` : `/`" class="brand-logo">
                    <!-- <img
                        src="https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2019/06/organic-store-logo5.svg"
                        alt="logo"
                        class="logo"
                /> -->
                    {{ brandname }}
                </a>
                <a href="#" data-target="mobile-demo" class="sidenav-trigger"
                    ><i class="material-icons">menu</i></a
                >
                <ul id="nav-mobile" class="left hide-on-med-and-down">
                    <span v-show="categories.length < 3">
                        <li
                            v-for="category in categories"
                            :key="category.id"
                            @click="showCategoryEditEditor"
                        >
                            <router-link
                                :to="
                                    loggedIn
                                        ? `#!`
                                        : {
                                              name: `product-search-category`,
                                              params: {
                                                  category_name:
                                                      category.name ??
                                                      `category`,
                                              },
                                              query: {
                                                  additionalData:
                                                      category.id ??
                                                      `category_id`,
                                              },
                                          }
                                "
                                >{{ category.name }}</router-link
                            >
                        </li>
                    </span>
                    <li v-show="categories.length > 3">
                        <a
                            class="dropdown-trigger"
                            href="#"
                            data-target="dropdownCategory"
                            >Categories</a
                        >
                    </li>
                    <ul id="dropdownCategory" class="dropdown-content">
                        <li
                            v-for="category in categories"
                            :key="category.id"
                            @click="showCategoryEditEditor"
                        >
                            <router-link
                                :to="
                                    loggedIn
                                        ? '#!'
                                        : {
                                              name: 'product-search-category',
                                              params: {
                                                  category_name:
                                                      category.name ??
                                                      'category',
                                              },
                                              query: {
                                                  additionalData:
                                                      category.id ??
                                                      'category_id',
                                              },
                                          }
                                "
                                >{{ category.name }}</router-link
                            >
                        </li>
                    </ul>
                </ul>

                <ul id="nav-mobile" class="right hide-on-med-and-down">
                    <li>
                        <a href="#" class="links-right">Blog</a>
                    </li>
                    <li>
                        <a :href="mailUs" class="links-right">Contact Us</a>
                    </li>
                    <li>
                        <router-link
                            :to="{ name: `Cart` }"
                            class="span relative"
                        >
                            <span class="numbers">$0.00</span>
                            <i class="fa-solid fa-cart-shopping cart"></i>
                            <span class="num">{{ cartCount }}</span>
                        </router-link>
                    </li>
                    <li>
                        <a
                            href="/auth/signin"
                            class="user"
                            v-if="!isAuthenticated"
                            >LOGIN/REGISTER</a
                        >
                        <a
                            v-else
                            :href="
                                role == `Admin`
                                    ? `/vendor/dashboard`
                                    : `/your_account/dashboard`
                            "
                            class="user"
                            >{{ names }}</a
                        >
                    </li>
                </ul>
            </div>
        </nav>
        <br />
    </div>
</template>
<script>
    import apiMixin from "../../mixin/apiMixin";
    import { useCartStore } from "../../../store";
    export default {
        mixins: [apiMixin],
        data() {
            return {
                isOpen: false,
            };
        },
        mounted() {
            localStorage.setItem("previousPage", this.$route.fullPath);
            var dropdowns = document.querySelectorAll(".dropdown-trigger");
            for (var i = 0; i < dropdowns.length; i++) {
                M.Dropdown.init(dropdowns[i]);
            }
        },
        computed: {
            isAuthenticated() {
                const cartStore = useCartStore();
                return cartStore.isAuthenticated;
            },
            names() {
                const cartStore = useCartStore();
                const names = cartStore.user.names;
                const nameParts = names.split(" ");
                return nameParts[0];
            },
            role() {
                const cartStore = useCartStore();
                const role = cartStore.user.role;
                return role;
            },
            cartCount() {
                const cartStore = useCartStore();
                return cartStore.cartCount;
            },
            wishlistCount() {
                return useCartStore().wishlistItemCount;
            },
            mailUs() {
                return (
                    `mailto:` +
                    this.email +
                    `?subject=Contact%20Us&body=Hello%20Team`
                );
            },
        },
        methods: {
            //   setActiveItem(item) {
            //     this.activeItem = item;
            //   },
            searchProducts() {
                // Add your search logic here
            },
            displaySearchbar() {
                this.showSearchbar = !this.showSearchbar;
            },
            showCategoryEditEditor() {
                if (this.loggedIn) {
                    this.$emit("showEditNavMenu", true);
                }
            },
        },
        props: {
            brandname: String,
            categories: Array,
            loggedIn: Boolean,
            email: String,
        },
        watch: {},
    };
</script>
<style scoped>
    i * {
        font-family: "Inter", sans-serif;
        font-family: "Jost", sans-serif;
        font-family: "Open Sans", sans-serif;
        margin-right: 0%;
    }

    .nav {
        align-items: center;
        background-color: white;
        color: black;
        box-shadow: none;
        height: 8vh;
        line-height: 8vh;
        padding: 1vh 2vw;
        font-family: "Inter", sans-serif;
        font-family: "Jost", sans-serif;
        font-family: "Open Sans", sans-serif;
    }

    ul li a {
        color: rgb(78, 78, 78);
        font-size: 110%;
        font-weight: 100%;
    }

    ul li a:hover {
        color: rgb(140, 194, 74);
        font-size: 110%;
        font-weight: 100%;
        background-color: white;
    }

    .left {
        margin-left: 13%;
    }

    .brand-logo {
        margin-left: 2%;
    }

    .logo {
        width: 10vw;
    }

    .right {
        margin-right: 4%;
    }

    .span-num {
        display: flex;
        justify-content: space-between;
        position: relative;
    }

    .numbers {
        color: rgb(140, 194, 74);
        font-size: large;
        margin-right: 1vw;
    }

    .span {
        color: rgb(140, 194, 74);
    }

    .cart {
        position: relative;

        font-size: 140%;
    }

    .num {
        border-radius: 100%;
        background-color: rgb(140, 194, 74);
        color: white;
        position: absolute;
        align-items: center;
        justify-content: center;
        font-size: 70%;
        width: 2.5vh;
        height: 2.5vh;
        position: absolute;
        line-height: 2.5vh;
        text-align: center;
        left: 93.3%;
        bottom: 0;
        top: 30%;
    }

    .user {
        margin-left: 1vw;
        font-size: 120%;
    }

    .links-right {
        margin-left: 2vw;
        margin-right: 1vw;
    }

    .nav a {
        color: black;
    }
    @media only screen and (min-width: 1024px) {
        .topbar {
            border-bottom: 1px solid #7c7c7c38;
            padding: 1vh 0;
        }
        .topbar-content {
            display: flex;
            justify-content: space-between;
        }
        .container {
            width: 85%;
        }
        .flex-right {
            display: flex;
            align-items: center;
            gap: 3vh;
        }

        .flex-right a {
            font-size: 0.813rem;
            /* font-size: 1.12525rem; */
            color: #334141;
        }

        .flex-right i {
            padding-right: 1vh;
        }

        .divider {
            height: 2vh;
            width: 0.05vh;
            background-color: black;
        }
        nav {
            background-color: #fff;
            box-shadow: none;
            padding: 3vh 0;
            line-height: unset;
        }
        nav .logo svg {
            width: 9.375rem;
        }
        nav a {
            color: #334141;
        }
        .flexed {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        nav .nav-wrapper i {
            line-height: 1;
        }
        .trigger i {
            font-size: 1.8rem !important;
        }
        .trigger.sidenav-trigger {
            display: block !important;
        }
        .allDeptBtn {
            background-color: #fed700;
            color: #333e48;
            padding: 1.5vh 4vh;
            font-weight: 700;
            border: none;
            font-size: inherit;
            border-top-right-radius: 1rem;
            border-top-left-radius: 1rem;
            font-family: "Open Sans", Helvetica, Arial, sans-serif;
        }
    }

    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        nav .brand-logo {
            left: 10%;
        }
        nav {
            background-color: #fed700;
            box-shadow: none;
            color: #333e48;
            height: 63px;
            line-height: 63px;
            padding: 2vh;
        }
        nav .nav-wrapper {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        nav .sidenav-trigger {
            margin: 0;
            position: unset;
            left: 5%;
            color: #333e48;
        }

        nav ul a {
            padding: 0;
            color: #333e48;
        }

        .brand-logo {
            color: #333e48;
        }

        .end {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 3vh;
        }

        .end i {
            font-size: 1.42rem;
            line-height: unset;
        }
    }

    @media only screen and (max-width: 767px) {
        nav .brand-logo {
            left: 25%;
        }
        nav {
            background-color: #fed700;
            box-shadow: none;
            color: #333e48;
            height: 63px;
            line-height: 63px;
            padding: 2vh;
        }
        nav .nav-wrapper {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        nav .sidenav-trigger {
            margin: 0;
            position: unset;
            left: 5%;
            color: #333e48;
        }

        nav ul a {
            padding: 0;
            color: #333e48;
        }

        .brand-logo {
            color: #333e48;
        }

        .end {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 3vh;
        }

        .end i {
            font-size: 1.42rem;
            line-height: unset;
        }
    }
</style>