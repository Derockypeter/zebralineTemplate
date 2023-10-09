<template>
    <div class="row row-cust">
        <h6 class="customer-title">Customers Reviews</h6>

        <div class="col s4">
            <div class="card-customer">
                <div class="elementor-background-overlay"></div>
                <div class="ratings">
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                </div>
                <p class="cust-text">
                    Click edit button to change this text. Lorem ipsum dolor sit
                    amet, consectetur adipiscing elit. Ut elit tellus, luctus
                    nec ullamcorper mattis, pulvinar dapibus leo.
                </p>
                <div class="profile">
                    <img
                        src="https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2019/07/client02-free-img.png"
                        alt="girl"
                    />
                    <p class="profile-name">Mila Kunis</p>
                </div>
            </div>
        </div>

        <div class="col s4">
            <div class="card-customers">
                <h6 class="cust-title">
                    Deal Of The Day 15% Off On All Vegetables!
                </h6>
                <p class="customer-text">
                    I am text block. Click edit button to change this tex em
                    ips.
                </p>
                <button class="cust-btn">
                    SHOP NOW<i class="fa-solid fa-arrow-right feat-arrow"></i>
                </button>
            </div>
        </div>

        <div class="col s4">
            <div class="card-customer">
                <div class="ratings">
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                </div>
                <p class="cust-text">
                    Click edit button to change this text. Lorem ipsum dolor sit
                    amet, consectetur adipiscing elit. Ut elit tellus, luctus
                    nec ullamcorper mattis, pulvinar dapibus leo.
                </p>
                <div class="profile">
                    <img
                        src="https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2019/07/client01-free-img.png"
                        alt="girl"
                    />
                    <p class="profile-name">Mike Sendler</p>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
    /* Customer Reviews Styling */

    .row-cust {
        padding: 8vw;
        /* background-image: url(https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2019/06/logo-leaf2-free-img.png);
            background-position: top left;
            background-repeat: no-repeat;
            background-size: 37% auto;
            opacity: 1; */
        background-color: rgb(248, 246, 242);
    }

    .cust-title {
        text-align: center;
        margin-top: 10vh;
        margin-bottom: 0vh;
        font-size: 200%;
        font-family: "Merriweather", serif;
    }

    .customer-title {
        text-align: center;
        margin-top: 2vh;
        margin-bottom: 15vh;
        font-size: 200%;
        font-family: "Merriweather", serif;
    }

    .card-customer {
        width: 100%;
        padding: 40px 40px 100px;
        background-color: white;
    }

    .ratings {
        color: rgb(225, 195, 24);
        text-align: center;
        margin-top: 2vh;
    }

    .cust-text {
        text-align: center;
        font-weight: 300;
        font-size: 110%;
        margin-top: 3vh;
    }

    .profile {
        display: flex;
        margin-top: 4vh;
        align-items: center;
        margin-left: 5vw;
    }

    .profile-name {
        margin-left: 1vw;
    }

    .card-customers {
        width: 100%;
        padding: 40px 40px 100px;
        background-image: url(https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2019/06/sydney-rae-668606-unsplash.jpg);
        background-size: cover;
        background-color: black;
        /* opacity: .15; */
        color: white;
        font-size: 130%;
        margin-bottom: 20%;
    }

    .customer-text {
        text-align: center;
        padding: 0%;
        margin-top: 0%;
    }

    .cust-btn {
        width: 60%;
        padding: 5%;
        background-color: var(--primary-color);
        border: 0px solid transparent;
        color: white;
        margin-right: 20vw;
        border-radius: 5%;
        margin-left: 4vw;
    }
</style>
<script>
    export default {};
</script>