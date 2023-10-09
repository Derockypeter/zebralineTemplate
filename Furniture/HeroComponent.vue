<template>
    <div>
        <div class="background-image">
            <div class="overlay"></div>
            <div class="max-width-640 mx-auto flex">
                <div class="flex justify-center flex-col items-center">
                    <h1 class="adText center">Work from Home Setups</h1>
                    <div class="divider center"></div>
                    <p class="center desc">
                        Porta tellus suscipit eget arcu eu nec quis scelerisque
                        nam vitae, turpis integer iaculis tristique vivamus
                        mattis egestas.
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
    .background-image {
        background: #8b8698;
        background: url("https://websitedemos.net/office-furniture-store-04/wp-content/uploads/sites/913/2021/07/furniture-store-home-office-page-header-img-bg.jpg");
        position: absolute;
        background-repeat: no-repeat;
        background-position: center center;
        background-size: cover;
        top: 0;
        padding-top: 100px;
        width: 100%;
    }
    .relative {
        position: relative;
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
    .mx-auto {
        margin-right: auto;
        margin-left: auto;
    }
    .max-width-640 {
        max-width: 66vh;
        min-height: 65vh;
        z-index: 1;
    }
    .adText {
        color: #fff;
        font-family: "Lexend", sans-serif;
        margin: 0;
        font-size: 4.8rem;
        font-weight: 600;
        z-index: 1;
    }
    .divider {
        width: 10%;
        margin: 3vh 0;
        background: #fbd84b;
        z-index: 1;
    }
    .desc {
        color: #ffffff;
        text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
        font-family: "Inter", sans-serif;
        z-index: 1;
    }
    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        .max-width-640 {
            max-width: 620px;
            min-height: 30vh;
        }
    }
    @media only screen and (max-width: 767px) {
        .max-width-640 {
            max-width: 50vh;
            min-height: 370px;
        }
        .adText {
            font-size: 2.25rem;
        }
    }
</style>