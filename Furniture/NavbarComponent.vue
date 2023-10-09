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
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        xmlns:xlink="http://www.w3.org/1999/xlink"
                        version="1.1"
                        id="ast-basket-icon-svg"
                        x="0px"
                        y="0px"
                        width="100"
                        height="100"
                        viewBox="826 826 140 140"
                        enable-background="new 826 826 140 140"
                        xml:space="preserve"
                    >
                        <path
                            d="M955.418,887.512c2.344,0,4.343,0.829,6.002,2.486c1.657,1.659,2.486,3.659,2.486,6.002c0,2.343-0.829,4.344-2.486,6.001  c-1.659,1.658-3.658,2.487-6.002,2.487h-0.994l-7.627,43.9c-0.354,2.033-1.326,3.713-2.917,5.04  c-1.593,1.326-3.405,1.989-5.438,1.989h-84.883c-2.033,0-3.846-0.663-5.438-1.989c-1.591-1.327-2.564-3.007-2.918-5.04l-7.626-43.9  h-0.995c-2.343,0-4.344-0.829-6.001-2.487c-1.658-1.657-2.487-3.658-2.487-6.001c0-2.343,0.829-4.343,2.487-6.002  c1.658-1.658,3.659-2.486,6.001-2.486H955.418z M860.256,940.563c1.149-0.089,2.111-0.585,2.885-1.491  c0.773-0.907,1.116-1.936,1.028-3.085l-2.122-27.586c-0.088-1.15-0.585-2.111-1.492-2.885c-0.906-0.774-1.934-1.117-3.083-1.028  c-1.149,0.088-2.111,0.586-2.885,1.492s-1.116,1.934-1.028,3.083l2.122,27.587c0.088,1.105,0.542,2.034,1.359,2.785  c0.818,0.752,1.78,1.128,2.885,1.128H860.256z M887.512,936.319v-27.587c0-1.149-0.42-2.144-1.26-2.984  c-0.84-0.84-1.834-1.26-2.984-1.26s-2.144,0.42-2.984,1.26c-0.84,0.841-1.26,1.835-1.26,2.984v27.587c0,1.149,0.42,2.145,1.26,2.984  c0.84,0.84,1.835,1.26,2.984,1.26s2.144-0.42,2.984-1.26C887.092,938.464,887.512,937.469,887.512,936.319z M912.977,936.319  v-27.587c0-1.149-0.42-2.144-1.26-2.984c-0.841-0.84-1.835-1.26-2.984-1.26s-2.145,0.42-2.984,1.26  c-0.84,0.841-1.26,1.835-1.26,2.984v27.587c0,1.149,0.42,2.145,1.26,2.984s1.835,1.26,2.984,1.26s2.144-0.42,2.984-1.26  C912.557,938.464,912.977,937.469,912.977,936.319z M936.319,936.65l2.122-27.587c0.088-1.149-0.254-2.177-1.027-3.083  s-1.735-1.404-2.885-1.492c-1.15-0.089-2.178,0.254-3.084,1.028c-0.906,0.773-1.404,1.734-1.492,2.885l-2.122,27.586  c-0.088,1.149,0.254,2.178,1.027,3.085c0.774,0.906,1.736,1.402,2.885,1.491h0.332c1.105,0,2.066-0.376,2.885-1.128  C935.777,938.685,936.23,937.756,936.319,936.65z M859.66,855.946l-6.167,27.322h-8.753l6.698-29.245  c0.84-3.89,2.807-7.062,5.902-9.516c3.095-2.453,6.632-3.68,10.611-3.68h11.074c0-1.149,0.42-2.144,1.26-2.984  c0.84-0.84,1.835-1.26,2.984-1.26h25.465c1.149,0,2.144,0.42,2.984,1.26c0.84,0.84,1.26,1.834,1.26,2.984h11.074  c3.979,0,7.516,1.227,10.611,3.68c3.094,2.454,5.062,5.626,5.901,9.516l6.697,29.245h-8.753l-6.168-27.322  c-0.486-1.945-1.491-3.537-3.017-4.774c-1.525-1.238-3.282-1.857-5.272-1.857h-11.074c0,1.15-0.42,2.144-1.26,2.984  c-0.841,0.84-1.835,1.26-2.984,1.26h-25.465c-1.149,0-2.144-0.42-2.984-1.26c-0.84-0.84-1.26-1.834-1.26-2.984h-11.074  c-1.99,0-3.747,0.619-5.272,1.857C861.152,852.409,860.146,854,859.66,855.946z"
                        ></path>
                    </svg>
                    <span class="cartCount">{{ cartCount }}</span>
                </router-link>
                <a href="#" data-target="mobile-demo" class="sidenav-trigger"
                    ><i class="material-icons">menu</i></a
                >
                <ul id="nav-mobile" class="right hide-on-med-and-down flex">
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
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                xmlns:xlink="http://www.w3.org/1999/xlink"
                                version="1.1"
                                id="ast-basket-icon-svg"
                                x="0px"
                                y="0px"
                                width="100"
                                height="100"
                                viewBox="826 826 140 140"
                                enable-background="new 826 826 140 140"
                                xml:space="preserve"
                            >
                                <path
                                    d="M955.418,887.512c2.344,0,4.343,0.829,6.002,2.486c1.657,1.659,2.486,3.659,2.486,6.002c0,2.343-0.829,4.344-2.486,6.001  c-1.659,1.658-3.658,2.487-6.002,2.487h-0.994l-7.627,43.9c-0.354,2.033-1.326,3.713-2.917,5.04  c-1.593,1.326-3.405,1.989-5.438,1.989h-84.883c-2.033,0-3.846-0.663-5.438-1.989c-1.591-1.327-2.564-3.007-2.918-5.04l-7.626-43.9  h-0.995c-2.343,0-4.344-0.829-6.001-2.487c-1.658-1.657-2.487-3.658-2.487-6.001c0-2.343,0.829-4.343,2.487-6.002  c1.658-1.658,3.659-2.486,6.001-2.486H955.418z M860.256,940.563c1.149-0.089,2.111-0.585,2.885-1.491  c0.773-0.907,1.116-1.936,1.028-3.085l-2.122-27.586c-0.088-1.15-0.585-2.111-1.492-2.885c-0.906-0.774-1.934-1.117-3.083-1.028  c-1.149,0.088-2.111,0.586-2.885,1.492s-1.116,1.934-1.028,3.083l2.122,27.587c0.088,1.105,0.542,2.034,1.359,2.785  c0.818,0.752,1.78,1.128,2.885,1.128H860.256z M887.512,936.319v-27.587c0-1.149-0.42-2.144-1.26-2.984  c-0.84-0.84-1.834-1.26-2.984-1.26s-2.144,0.42-2.984,1.26c-0.84,0.841-1.26,1.835-1.26,2.984v27.587c0,1.149,0.42,2.145,1.26,2.984  c0.84,0.84,1.835,1.26,2.984,1.26s2.144-0.42,2.984-1.26C887.092,938.464,887.512,937.469,887.512,936.319z M912.977,936.319  v-27.587c0-1.149-0.42-2.144-1.26-2.984c-0.841-0.84-1.835-1.26-2.984-1.26s-2.145,0.42-2.984,1.26  c-0.84,0.841-1.26,1.835-1.26,2.984v27.587c0,1.149,0.42,2.145,1.26,2.984s1.835,1.26,2.984,1.26s2.144-0.42,2.984-1.26  C912.557,938.464,912.977,937.469,912.977,936.319z M936.319,936.65l2.122-27.587c0.088-1.149-0.254-2.177-1.027-3.083  s-1.735-1.404-2.885-1.492c-1.15-0.089-2.178,0.254-3.084,1.028c-0.906,0.773-1.404,1.734-1.492,2.885l-2.122,27.586  c-0.088,1.149,0.254,2.178,1.027,3.085c0.774,0.906,1.736,1.402,2.885,1.491h0.332c1.105,0,2.066-0.376,2.885-1.128  C935.777,938.685,936.23,937.756,936.319,936.65z M859.66,855.946l-6.167,27.322h-8.753l6.698-29.245  c0.84-3.89,2.807-7.062,5.902-9.516c3.095-2.453,6.632-3.68,10.611-3.68h11.074c0-1.149,0.42-2.144,1.26-2.984  c0.84-0.84,1.835-1.26,2.984-1.26h25.465c1.149,0,2.144,0.42,2.984,1.26c0.84,0.84,1.26,1.834,1.26,2.984h11.074  c3.979,0,7.516,1.227,10.611,3.68c3.094,2.454,5.062,5.626,5.901,9.516l6.697,29.245h-8.753l-6.168-27.322  c-0.486-1.945-1.491-3.537-3.017-4.774c-1.525-1.238-3.282-1.857-5.272-1.857h-11.074c0,1.15-0.42,2.144-1.26,2.984  c-0.841,0.84-1.835,1.26-2.984,1.26h-25.465c-1.149,0-2.144-0.42-2.984-1.26c-0.84-0.84-1.26-1.834-1.26-2.984h-11.074  c-1.99,0-3.747,0.619-5.272,1.857C861.152,852.409,860.146,854,859.66,855.946z"
                                ></path>
                            </svg>
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
                            <svg
                                version="1.1"
                                class="account-icon"
                                xmlns="http://www.w3.org/2000/svg"
                                xmlns:xlink="http://www.w3.org/1999/xlink"
                                x="0px"
                                y="0px"
                                viewBox="0 0 120 120"
                                enable-background="new 0 0 120 120"
                                xml:space="preserve"
                            >
                                <path
                                    d="M84.6,62c-14.1,12.3-35.1,12.3-49.2,0C16.1,71.4,3.8,91,3.8,112.5c0,2.1,1.7,3.8,3.8,3.8h105c2.1,0,3.8-1.7,3.8-3.8 C116.2,91,103.9,71.4,84.6,62z"
                                ></path>
                                <circle cx="60" cy="33.8" r="30"></circle>
                            </svg>
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
        mixins: [apiMixin],
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
        bottom: 50%;
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
        background-color: #fade5f;
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