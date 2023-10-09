<template>
    <div class="offer" @click="showHeroEditor">
        <h6 class="offer-text">Get 25% Off On Your First Purchase!</h6>
        <button class="offer-btn">
            <i class="fa-solid fa-cart-shopping offer-shop"></i>
            SHOP NOW
        </button>
    </div>
</template>
<script>
    export default {
        mounted() {
            // Initialize Materialize components
            M.AutoInit();
        },
        methods: {
            showHeroEditor() {
                if (this.loggedIn) {
                    this.$emit("showHeroEditor", true);
                }
            },
        },
        props: {
            loggedIn: Boolean,
            hero: Object,
        },
    };
</script>
<style scoped>
    /* Offer Section Styling */

    .offer {
        padding: 4vw;
        background-color: black;
        color: white;
        display: flex;
        justify-content: space-between;
    }

    .offer-text {
        font-size: 200%;
        font-weight: 500;
        font-family: 'Merriweather', serif;
        margin-left: 5vw;
    }

    .offer-btn {
        width: 15%;
        padding: 1%;
        background-color: var(--primary-color);
        border: 0px solid transparent;
        color: white;
        margin-right: 20vw;
        border-radius: 5%;
    }

    .offer-shop {
        margin-right: 1vw;
    }
    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        button {
            padding: 0.5rem 3rem;
        }
    }
    @media only screen and (max-width: 767px) {
        .overflow-auto {
            overflow: auto;
        }
        .flex-shrink-0 {
            flex-shrink: 0;
        }
        .justify-center {
            justify-content: flex-start;
        }
    }
</style>