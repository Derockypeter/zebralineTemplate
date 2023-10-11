<template>
    <div>
        <nav>
            <div class="nav">
                <a
                    :href="loggedIn ? `#!` : `/`"
                    class="brand-logo hide-on-large-only"
                >
                    <span class="brandname">{{ brandname }}</span>
                </a>

                <span class="hide-on-large-only mobileNavRight">
                    <router-link
                        :to="{ name: `Cart` }"
                        class="iconLinks shoppingCartIconContainer mg-rt-2"
                    >
                        <i
                            class="material-icons themeTextColor mobileShoppingIcon"
                            >shopping_basket</i
                        >
                        <span class="notify">{{ cartCount }}</span>
                    </router-link>
                    <a
                        href="#"
                        data-target="mobile-demo"
                        class="sidenav-trigger"
                        ><i class="material-icons">menu</i></a
                    >
                </span>

                <div class="centerFlex hide-on-med-and-down">
                    <a href="/" class="brandLogo"
                        ><span class="brandname">{{ brandname }}</span></a
                    >

                    <ul class="navLinks">
                        <li>
                            <a :href="loggedIn ? `#!` : `/`">Home</a>
                        </li>
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

                <div class="centerFlex hide-on-med-and-down">
                    <ul class="centerFlex">
                        <li>
                            <a
                                href="/auth/signin"
                                class="authLink"
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
                                >{{ names }}</a
                            >
                        </li>
                        <li>
                            <a
                                href="#"
                                class="iconLinks"
                                @click="displaySearchbar()"
                                ><i class="material-icons">search</i></a
                            >
                        </li>
                        <li>
                            <a href="#" class="iconLinks withNotifier">
                                <i class="material-icons">favorite_border</i>
                                <span class="notify">{{ wishlistCount }}</span>
                            </a>
                        </li>
                        <li>
                            <router-link
                                :to="{ name: `Cart` }"
                                class="iconLinks withNotifier"
                            >
                                <i class="material-icons">shopping_cart</i>
                                <span class="notify">{{ cartCount }}</span>
                            </router-link>
                        </li>
                    </ul>
                </div>
            </div>
            <div v-if="showSearchbar" class="searchbar">
                <div class="input-field">
                    <input id="search" type="search" v-model="searchData" />
                    <label class="label-icon" for="search"
                        ><i class="material-icons">search</i></label
                    >
                    <i class="material-icons" @click="displaySearchbar()"
                        >close</i
                    >
                </div>
            </div>
        </nav>
        <ul class="sidenav" id="mobile-demo">
            <li class="mobileSidNavBrand">
                <a :href="loggedIn ? `#!` : `/`"
                    ><span class="brandname">{{ brandname }}</span></a
                >
            </li>
            <li
                v-for="category in categories.slice(0, 3)"
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
                                          category.name ?? `category`,
                                  },
                                  query: {
                                      additionalData:
                                          category.id ?? `category_id`,
                                  },
                              }
                    "
                    >{{ category.name }}</router-link
                >
            </li>
            <li>
                <a href="#"> Blog </a>
            </li>
            <li>
                <a :href="mailUs">Contact Us</a>
            </li>

            <li class="divider" tabindex="-1"></li>

            <li>
                <a href="/auth/signin" class="authLink" v-if="!isAuthenticated">
                    <i class="material-icons">person</i>
                    LOGIN/REGISTER
                </a>
                <router-link
                    v-else
                    :to="
                        role == `Admin`
                            ? `/vendor/dashboard`
                            : `/your_account/dashboard`
                    "
                    >{{ names }}</router-link
                >
            </li>

            <li>
                <a href="#" class="authLink mobileWishist">
                    <span>
                        <i class="material-icons">favorite_border</i>
                        Wishlist
                    </span>

                    <span class="notify">{{ wishlistCount }}</span>
                </a>
            </li>
            <li>
                <a href="#" class="authLink" @click="displaySearchbar()"
                    ><i class="material-icons">search</i></a
                >
            </li>
        </ul>
        <div v-if="showSearchbar" class="searchbar">
            <div class="input-field">
                <input id="search" type="search" v-model="searchData" />
                <label class="label-icon" for="search"
                    ><i class="material-icons">search</i></label
                >
                <i class="material-icons" @click="displaySearchbar()">close</i>
            </div>
        </div>
    </div>
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
    nav {
        background-color: #ffffff;
        height: 10vh;
    }
    .nav {
        width: 100%;
        height: 10vh;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 1vh 1vw;
    }
    .centerFlex {
        display: flex;
        align-items: center;
    }
    a.brandLogo {
        display: flex;
        align-items: center;
        color: #24262b;
    }
    .brandLogo .brandname {
        margin-left: 1vw;
        font-size: 1.5rem;
        font-weight: 600;
    }
    ul.navLinks {
        display: flex;
        margin: 0;
        margin-left: 5vw;
    }
    ul.navLinks li a {
        padding: 0 0.7vw;
    }
    ul li a {
        text-decoration: none;
        text-transform: uppercase;
        color: #24262b;
        font-weight: 400;
        font-size: 1.1rem;
    }
    ul li a.iconLinks {
        padding: 0 1vw;
    }
    ul li a.authLink {
        margin-right: 2vw;
    }
    ul li a.authLink:hover {
        transition: unset;
        background-color: unset !important;
    }
    ul li a:hover {
        color: var(--primary-color);
        background-color: unset !important;
    }
    nav i.material-icons {
        color: #24262b;
    }
    .iconLinks.withNotifier {
        display: flex;
        cursor: pointer;
    }
    .iconLinks .notify {
        background-color: var(--primary-color);
        color: #ffffff;
        font-size: 0.7rem;
        padding: 0 0.2vw;
        border-radius: 30%;
        height: 1.8vh;
        line-height: 1.8vh;
        position: relative;
        right: 0.7vw;
        bottom: -4vh;
    }

    .searchbar {
        background-color: rgba(0, 0, 0, 0.6);
        position: absolute;
        width: 100%;
        top: 0;
        height: 10vh;
    }
    .searchbar .input-field {
        background-color: #ffffff;
        width: 50%;
        margin: 0 auto;
        height: 10vh;
    }
    .searchbar .input-field input {
        padding: 0 0 0 5%;
        width: 95%;
        margin-bottom: 0;
        height: inherit;
    }
    .searchbar .input-field label,
    .searchbar .input-field i {
        height: 10vh;
        line-height: 10vh;
    }
    .input-field input[type="search"] + .label-icon {
        left: 0.5rem;
    }

    /* MOBILE */
    @media only screen and (max-width: 767px) {
        nav {
            background-color: #ffffff;
            height: 7vh;
        }
        nav .nav {
            display: flex;
            justify-content: space-between;
            padding: 0 3vw;
            height: 7vh;
            line-height: 7vh;
        }
        nav .brand-logo {
            left: unset;
            -webkit-transform: unset;
            transform: unset;
            color: var(--primary-color);
            position: unset;
        }
        nav a {
            color: var(--primary-color);
        }
        nav .sidenav-trigger {
            float: unset;
            position: unset;
            margin: 0;
            height: 5vh;
            line-height: 5vh;
        }
        nav .sidenav-trigger i {
            padding: 0 2.5vw;
            height: 5vh;
            line-height: 5vh;
            color: #fff;
            background-color: var(--primary-color);
        }
        .sidenav li > a > i {
            margin-right: 2vw;
        }
        nav i.material-icons {
            font-size: 2rem;
        }

        .mobileNavRight {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .themeTextColor {
            color: var(--primary-color);
        }
        .shoppingCartIconContainer {
            position: relative;
        }
        .mobileShoppingIcon {
            height: 5vh;
            line-height: 6vh;
            font-size: 1.7rem !important;
        }
        .mg-rt-2 {
            margin-right: 2vw;
        }
        .iconLinks .notify {
            height: 1.8vh;
            line-height: 1.8vh;
            font-size: 0.5rem;
            padding: 0 1vw;
            border-radius: 50%;
            position: absolute;
            right: 3.8vw;
            bottom: 2.5vh;
        }
        .mobileWishist {
            display: flex;
            justify-content: space-between;
        }
        .mobileWishist i {
            position: relative;
            top: 0.4vh;
            font-size: 1.6rem;
            margin-right: 2vw;
        }
        .mobileSidNavBrand,
        .mobileSidNavBrand a {
            height: 10vh;
            line-height: 10vh;
        }
        .mobileSidNavBrand a {
            background-color: var(--primary-color);
            color: black;
        }
    }
</style>