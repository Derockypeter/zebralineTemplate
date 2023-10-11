<template>
    <div>
        <NavbarComponent :brandname="brandname" :categories="categories" :loggedIn="loggedIn" @showEditNavMenu="showEditNavMenu($event)" :email="email"/>
        <HeroComponent :loggedIn="loggedIn" @showHeroEditor="showHeroEditor($event)" :hero="hero" :timestamp="timestamp" />
        <CategoryComponent :categories="categories" />
        <FeaturedProductsComponent :products="products" @showProductEditor="showProductEditor" :loggedIn="loggedIn"/>
        <BlogComponent />
        <OffersComponent :loggedIn="loggedIn" @showHeroEditor="showHeroEditor($event)" :hero="hero" :timestamp="timestamp" :offers="offers"/>
        <SellingPointComponent @showSellingPointEditor="showSellingPointEditor($event)" :loggedIn="loggedIn" :sellPoint="sellPoint" />
        <FooterComponent :brandname="brandname" :categories="categories" />
    </div>
</template>

<script>
import CategoryComponent from './CategoryComponent.vue';
import FeaturedProductsComponent from './FeaturedProductsComponent.vue';
import HeroComponent from './HeroComponent.vue';
import NavbarComponent from './NavbarComponent.vue';
import OffersComponent from './OffersComponent.vue';
import FooterComponent from './FooterComponent.vue';
import BlogComponent from './BlogComponent.vue';
import SellingPointComponent from './SellingPointComponent.vue';

export default {
    components: { NavbarComponent, HeroComponent, OffersComponent, FeaturedProductsComponent, CategoryComponent, FooterComponent, SellingPointComponent, BlogComponent },
    props: {
        loggedIn: Boolean,

        themecolor: String,
        brandname: String,
        sellPoint: Array,
        categories: Array,
        hero: Object,
        offers: Array,
        products: Array,
        blog: Array,
        timestamp: Number,
        email: String,
    },
    methods: {
        showEditNavMenu (evt) {
            this.$emit('showEditNavMenu', evt);
            console.log('Home');
        },
        showHeroEditor (evt) {
            this.$emit('showHeroEditor', evt);
            console.log('Home');
        },
        showSellingPointEditor (evt) {
            this.$emit('showSellingPointEditor', evt);
            console.log('showSellingPointEditor');
        },
        showProductEditor(evt) {
            this.$emit('showProductEditor', evt);
        },
        
    },
    mounted() {
        
    }
}
</script>,