<template>
    <div class="">
        <div
            class="background-image top-90 absolute"
            :style="{ background: `url(${background})` }"
            @click="showHeroEditor"
        >
            <div class="overlay"></div>
            <div class="flex items-center flex-col">
                <div class="flex justify-center flex-col items-center">
                    <p class="center desc">Custom Setups.</p>
                    <h1 class="adText center">
                        Lets build your dream working place
                    </h1>
                    <button class="center">
                        <span>Shop Now</span
                        ><span
                            ><svg
                                xmlns="http://www.w3.org/2000/svg"
                                viewBox="0 0 2048 2048"
                            >
                                <path
                                    d="M6.125 1088h1797.89l-402.976 403 89.994 90L2048 1024l-556.966-557-89.994 90 402.976 403H6.125v128z"
                                ></path></svg
                        ></span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                background:
                    "https://websitedemos.net/office-furniture-store-04/wp-content/uploads/sites/913/2021/07/wfh-furniture-store-cta-img-bg.jpg",
            };
        },
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
    };
</script>
<style scoped>
    .flex {
        display: flex;
    }
    .justify-center {
        justify-content: center;
    }
    .flex-col {
        flex-direction: column;
    }
    .items-center {
        align-items: center;
    }
    .absolute {
        position: absolute;
    }
    .background-image {
        background-position: center center;
        background-repeat: no-repeat;
        background-size: cover;
        padding: 15vh 40vh;
        width: 100%;
    }
    .background-image > .overlay {
        background-color: #262527;
        opacity: 0.48;
        transition: background 0.3s, border-radius 0.3s, opacity 0.3s;
    }
    .background-image .overlay {
        height: 100%;
        width: 100%;
        top: 0;
        left: 0;
        position: absolute;
    }
    .top-90 {
        top: 600vh;
    }
    .desc {
        color: #f8f8f8;
        text-transform: uppercase;
        letter-spacing: 2px;
        line-height: 1.25rem;
        margin: 0;
        font-size: 0.93333333333333rem;
        z-index: 1;
        font-family: "Lexend", sans-serif;
        font-weight: 600;
        position: relative;
    }
    .adText {
        color: #f8f8f8;
        margin: 0;
        font-size: 4.5rem;
        z-index: 1;
        font-family: "Lexend", sans-serif;
        font-weight: 700;
        position: relative;
        padding: 4vh 0;
    }
    button {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 3vh;
        border-top-left-radius: 4px;
        border-top-right-radius: 4px;
        border-bottom-right-radius: 4px;
        border-bottom-left-radius: 4px;
        padding-top: 15px;
        padding-right: 31px;
        padding-bottom: 15px;
        padding-left: 31px;
        font-weight: 600;
        line-height: 1em;
        border-color: #fbd84b;
        background-color: #fbd84b;
        position: relative;
        z-index: 1;
        color: #26222f;
        font-size: 0.9375rem;
    }
    button svg {
        fill: #26222f;
        width: 1em;
        height: auto;
    }
    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        .adText {
            font-size: 3.5rem;
        }
        .desc {
            font-size: 0.86666666666667rem;
        }
        .background-image {
            padding: 10vh 10vh;
        }
        .top-90 {
            top: 335vh;
        }
    }
    @media only screen and (max-width: 767px) {
        .adText {
            font-size: 2rem;
        }
        .desc {
            font-size: 0.8rem;
        }
        .background-image {
            padding: 10vh 10vh;
        }
        .top-90 {
            top: 390vh;
        }
    }
</style>