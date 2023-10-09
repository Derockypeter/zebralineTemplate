<template>
    <div>
        <div class="points">
            <div class="row">
                <div class="col s3">
                    <div class="card">
                        <div class="point-icon">
                            <i class="fa-solid fa-truck text-point"></i>
                            <p class="point-word">Free Shipping</p>
                        </div>
                        <p class="shipping-text">Above $5 Only</p>
                    </div>
                </div>

                <div class="col s3">
                    <div class="card">
                        <div class="point-icon">
                            <i
                                class="fa-regular fa-address-book text-point"
                            ></i>
                            <p class="point-word">Organic Certified</p>
                        </div>
                        <p class="shipping-text">100% Guarantee</p>
                    </div>
                </div>

                <div class="col s3">
                    <div class="card">
                        <div class="point-icon">
                            <i
                                class="fa-regular fa-money-bill-1 text-point"
                            ></i>
                            <p class="point-word">Huge Savings</p>
                        </div>
                        <p class="shipping-text">At Lowest Price</p>
                    </div>
                </div>

                <div class="col s3">
                    <div class="card">
                        <div class="point-icon">
                            <i class="fa-solid fa-arrows-spin text-point"></i>
                            <p class="point-word">Easy Returns</p>
                        </div>
                        <p class="shipping-text">No Questions Asked</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
    /* Selling Points Sections */

    .points {
        background-color: black;
        color: white;
        line-height: 6vh;
        padding: 3%;
        align-items: center;
    }

    .card {
        background-color: rgb(48, 48, 48);
        margin: 0;
        padding: 0;
    }

    .selling-images {
        background-color: unset;
    }

    .text-point {
        margin-left: 2vw;
        font-size: 150%;
        color: rgb(115, 167, 52);
    }

    .point-icon {
        display: flex;
        align-items: center;
    }

    .point-word {
        margin-left: 1vw;
        margin-bottom: 0%;
        font-size: 120%;
        font-family: "Merriweather", serif;
    }

    .shipping-text {
        margin-left: 5vw;
        margin-top: 0%;
        margin-bottom: 0%;
        font-size: 100%;
        font-weight: 350;
        font-family: "Open Sans", sans-serif;
    }

    .row {
        margin: 0;
    }
</style>