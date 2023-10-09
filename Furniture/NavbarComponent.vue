<template>
    <section class="absolute">
        <nav>
            <div class="nav-wrapper flex justify-between">
                <div class="flex">
                    <a href="#" class="brandname">{{ brandname }}</a>
                    <ul id="nav-mobile" class="hide-on-med-and-down">
                        <li><a :href="loggedIn ? `#!` : `/`">Home</a></li>
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
                        <li>
                            <a href="#">Blog</a>
                        </li>
                        <li>
                            <a :href="mailUs">Contact Us</a>
                        </li>
                    </ul>
                </div>
                <router-link :to="{name: `Cart`}"  class="cartHolder relative hide-on-large-only">
                    <i class="material-icons">shopping_basket</i>
                    <span class="cartCount">{{ cartCount }}</span>
                </router-link>
                <a href="#" data-target="mobile-demo" class="sidenav-trigger"
                    ><i class="material-icons">menu</i></a
                >
                <ul id="nav-mobile" class="right hide-on-med-and-down flex items-center">
                    <li><a :href="loggedIn ? `#!` : `/`">Home</a></li>
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
                    <li>
                        <a href="#">Blog</a>
                    </li>
                    <li>
                        <a :href="mailUs">Contact Us</a>
                    </li>
                    <li>
                        <form action="" class="flex items-center">
                            <input
                                type="search"
                                class="browser-default"
                                placeholder="Search Products..."
                            />
                            <button
                                type="submit"
                                class="wc-block-product-search__button"
                                aria-label="Search"
                                aria-expanded="false"
                            >
                                <svg
                                    aria-hidden="true"
                                    role="img"
                                    focusable="false"
                                    class="dashicon dashicons-arrow-right-alt2"
                                    xmlns="http://www.w3.org/2000/svg"
                                    width="20"
                                    height="20"
                                    viewBox="0 0 20 20"
                                >
                                    <path d="M6 15l5-5-5-5 1-2 7 7-7 7z"></path>
                                </svg>
                            </button>
                        </form>
                    </li>
                    <li>
                        <router-link :to="{name: `Cart`}" class="cartHolder relative">
                            <i class="material-icons">shopping_basket</i>
                            <span class="cartCount">0</span>
                        </router-link>
                    </li>
                    <li>
                        <a
                            href="/auth/signin"
                            class="relative userIcon"
                            v-if="!isAuthenticated"
                            >LOGIN/REGISTER</a
                        >
                        <a class="userIcon relative" :href="role == `Admin` ? `/vendor/dashboard` : `/your_account/dashboard`">
                            <i class="material-icons">person</i>
                        </a>
                    </li>
                </ul>
            </div>
        </nav>
    </section>
</template>
<script>
    import apiMixin from "../../mixin/apiMixin";
    import { useCartStore } from "../../../store";
    export default {
        // mixins: [apiMixin],
        data() {
            return {
                showSearchbar: false,
                searchData: "",
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
                    console.log("am here");
                }
            },
            // #TODO: DO a mixin later for API
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
    .relative {
        position: relative;
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
        z-index: 1;
        width: 100%;
    }
    nav {
        background: transparent;
        font-family: "Inter", sans-serif;
        height: 100px;
        line-height: 100px;
        padding-left: 3vh;
        padding-right: 3vh;
        box-shadow: none;
        border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    }
    nav ul a {
        font-size: 0.9375rem;
    }
    .brandname {
        text-transform: uppercase;
        font-weight: 700;
        color: #f8f0ce;
        font-size: 2.1rem;
        padding: 0;
    }
    .cartHolder {
        font-size: 1.3em;
    }
    .cartHolder svg,
    .userIcon svg {
        width: 1.25rem;
        height: 1.2rem;
        fill: currentColor;
        vertical-align: middle;
    }
    .cartCount {
        display: inline-block;
        width: 1.5vh;
        height: 1.5vh;
        line-height: 1.5vh;
        text-align: center;
        background-color: #f8f8f8;
        color: #000;
        border-radius: 100%;
        font-weight: bold;
        font-size: 0.6875rem;

        position: absolute;
        bottom: 60%;
        right: 0;
    }
    nav ul a:hover {
        background-color: transparent;
    }
    form {
        padding: 0 1vh;
    }
    input[type="search"] {
        flex-grow: 1;
        line-height: 1.8;
        padding: 6px 8px;

        color: #666;
        padding: 0.75em;
        height: 4vh;
        border-width: 1px;
        border-style: solid;
        border-color: #dddd;
        border-radius: 2px;
        background: #fafafa;
        box-shadow: none;
        box-sizing: border-box;
        transition: all 0.2s linear;
    }

    .wc-block-product-search__button {
        height: 4vh;
        align-items: center;
        cursor: pointer;
        display: flex;
        margin: 0 0 0 6px;
        overflow: hidden;
        padding: 0 0.5em;
        position: relative;
        border: none;
        background-color: var(--primary-color);
    }

    .wc-block-product-search__button:focus {
        background-color: #f5dd73;
    }
    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        .sidenav-trigger {
            align-self: center;
            margin: 0;
        }
        .cartHolder {
            position: absolute;
            right: 10%;
        }
    }
    @media only screen and (max-width: 767px) {
        .sidenav-trigger {
            align-self: center;
            margin: 0;
        }
        .cartHolder {
            position: absolute;
            right: 20%;
        }
    }
</style>