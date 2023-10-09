<template>
  <div>
    <NavbarComponent :categories="categories"/>
    <HeroComponent />
    <CategoryComponent />
    <FeaturedProductsComponent />
    <BlogComponent />
    <OffersComponent />
    <ReviewsComponent />
    <FooterComponent />
  </div>
</template>
<script>
    import M from 'materialize-css'
    // import M from 'materialize-css'
    // import NavbarComponent from '../../../Electro/NavbarComponent.vue'
    // import HeroComponent from '../../../Electro/HeroComponent.vue'
    // import CategoryComponent from '../../../Electro/CategoryComponent.vue'
    // import FeaturedProductsComponent from '../../../Electro/FeaturedProductsComponent.vue'
    // import OffersComponent from '../../../Electro/OffersComponent.vue'
    // import FooterComponent from '../../../Electro/FooterComponent.vue'
    // import BlogComponent from '../../../Electro/BlogComponent.vue'
    // import ReviewsComponent from '../../../Electro/ReviewsComponent.vue'
    // import NavbarComponent from '../../../Furniture/NavbarComponent.vue'
    // import HeroComponent from '../../../Furniture/HeroComponent.vue'
    // import CategoryComponent from '../../../Furniture/CategoryComponent.vue'
    // import FeaturedProductsComponent from '../../../Furniture/FeaturedProductsComponent.vue'
    // import BlogComponent from '../../../Furniture/BlogComponent.vue'
    // import OffersComponent from '../../../Furniture/OffersComponent.vue'
    // import ReviewsComponent from '../../../Furniture/ReviewsComponent.vue'
    // import FooterComponent from '../../../Furniture/FooterComponent.vue'

    import NavbarComponent from '../../../Beauty/NavbarComponent.vue'
    import HeroComponent from '../../../Beauty/HeroComponent.vue'
    import CategoryComponent from '../../../Beauty/CategoryComponent.vue'
    import FeaturedProductsComponent from '../../../Beauty/FeaturedProductsComponent.vue'
    import BlogComponent from '../../../Beauty/BlogComponent.vue'
    import OffersComponent from '../../../Beauty/OffersComponent.vue'
    import ReviewsComponent from '../../../Beauty/ReviewsComponent.vue'
    import FooterComponent from '../../../Beauty/FooterComponent.vue'

    export default {
      components: {
        NavbarComponent,
        HeroComponent,
        CategoryComponent,
        FeaturedProductsComponent,
        BlogComponent,
        OffersComponent,
        ReviewsComponent,
        FooterComponent,
      },
      data(){
        return {
          categories: [],
        }
      },
      mounted() {
        M.AutoInit()
        document.addEventListener('DOMContentLoaded', function () {
          const selectTrigger = document.querySelector('#custom-select-trigger')
          const options = {
            alignment: 'bottom', // Set the dropdown alignment to bottom
            constrainWidth: false // Disable width constraint
          }
          M.FormSelect.init(selectTrigger, options)
        })
      }
    }
</script>
<style>
    body {
      font-family: 'Open Sans', Helvetica, Arial, sans-serif;
    }
</style>