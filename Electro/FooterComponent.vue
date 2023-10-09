<template>
    <div class="mt-4 bgGray">
        <div class="container">
            <div class="row">
                <div class="col s12 m12 l4">
                    <div class="brand-logo">
                        {{ brandname }}
                    </div>
                    <div class="flex items-center gap-2">
                        <i class="fa-solid fa-headset"></i>
                        <p>
                            <span class="callText"
                                >Got questions? Call us 24/7!</span
                            >
                            <span class="phone"
                                >(800) 8001-8588, (0600) 874548</span
                            >
                        </p>
                    </div>
                    <h6>Contact Info</h6>
                    <p class="address">
                        17 Princess Road, London, Greater London NW1 8JR, UK
                    </p>
                    <div class="flex">
                        <a href="" class="btnSocial">
                            <i class="fa-brands fa-facebook-f"></i>
                        </a>
                        <a href="" class="btnSocial"
                            ><i class="fa-brands fa-twitter"></i
                        ></a>
                        <a href="" class="btnSocial"
                            ><i class="fa-brands fa-instagram"></i
                        ></a>
                    </div>
                </div>
                <div class="col s12 m4 l3">
                    <h6>Find it fast</h6>

                    <ul class="">
                        <li>
                            <a href="">Laptops & Computers</a>
                        </li>
                        <li>
                            <a href="">Cameras & Photography</a>
                        </li>
                        <li>
                            <a href="">Smart Phones & Tablets</a>
                        </li>
                        <li>
                            <a href="">Video Games & Consoles</a>
                        </li>
                        <li>
                            <a href="">TV & Audio</a>
                        </li>
                        <li>
                            <a href="">Gadgets</a>
                        </li>
                        <li>
                            <a href="">Car Electronic & GPS</a>
                        </li>
                    </ul>
                </div>
                <div class="col s12 m4 l2">
                    <h6>&nbsp;</h6>
                    <ul class="">
                        <li>
                            <a href="">Printers and ink</a>
                        </li>
                        <li>
                            <a href="">Software</a>
                        </li>
                        <li>
                            <a href="">Office Supplies</a>
                        </li>
                        <li>
                            <a href="">Computer Componenents</a>
                        </li>
                        <li>
                            <a href="">Accessories</a>
                        </li>
                    </ul>
                </div>
                <div class="col s12 m4 l3">
                    <h6>Customer Service</h6>
                    <ul class="">
                        <li>
                            <a href="">My Account</a>
                        </li>
                        <li>
                            <a href="">Order Tracking</a>
                        </li>
                        <li>
                            <a href="">Wish List</a>
                        </li>
                        <li>
                            <a href="">Customer Service</a>
                        </li>
                        <li>
                            <a href="">FAQs</a>
                        </li>
                        <li>
                            <a href="">Product Support</a>
                        </li>
                        <li>
                            <a href="">Returns and Exchange</a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="bg-grey">
            <div class="container">
                <div class="flex gap-2">
                    <p>© {{ brandname }}</p>
                    - <span>Powered by Zebraline</span>
                </div>
            </div>
        </div>
        <button id="scrollToTopButton" class="scroll-to-top-button">
            <i class="material-icons">keyboard_arrow_up</i>
        </button>
    </div>
</template>
<style scoped>
    .mt-4 {
        margin-top: 4vh;
    }
    .logo {
        padding: 2vh 0;
    }
    .gap-2 {
        gap: 2vh;
    }
    .callText {
        font-size: 0.81288rem;
        font-weight: 300;
        display: block;
    }
    .phone {
        font-size: 1.25038rem;
        font-weight: 400;
    }
    .fa-headset {
        color: var(--primary-color);
        font-size: 3rem;
    }
    .btnSocial {
        display: inline-block;
        font-weight: 700;
        color: #333e48;
        text-align: center;
        vertical-align: middle;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        background-color: transparent;
        border: 1px solid transparent;
        padding: 0.67rem 1rem;
        font-size: 0.875rem;
        line-height: 1.5;
        border-radius: 1.4rem;
        transition: all 0.2s ease-in-out;
        font-size: 1.25038rem;
        width: 3.125rem;
        height: 3.125rem;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .btnSocial i {
        font-size: 1.5rem;
    }
    .btnSocial:hover {
        color: #fff;
        background: #333e48;
        box-shadow: 0 4px 11px rgba(51, 62, 72, 0.35);
    }
    li {
        padding: 0.32rem 1.25rem;
    }
    a {
        font-size: 0.875rem;
        color: #333e48;
    }
    a:hover {
        color: #000000;
    }
    h6 {
        font-weight: 700;
        padding-left: 1.25rem;
    }
    h6:first-of-type {
        padding: 0;
    }
    .container {
        width: 85%;
    }
    .bgGray {
        background-color: #f8f8f8 !important;
    }
    .address {
        font-size: 0.875rem;
        font-weight: 400;
        font-family: "Open Sans", Helvetica, Arial, sans-serif;
    }
    .bg-grey {
        background-color: #eaeaea !important;
        padding: 0.5rem 0;
    }
    .bg-grey p {
        margin: 0;
        font-weight: 700;
    }
    /* Add your other CSS styles here */

    /* Floating Scroll-to-Top Button */
    .scroll-to-top-button {
        position: fixed;
        bottom: 20px;
        right: 20px;
        background-color: var(--primary-color); /* Adjust the button's background color */
        color: #fff; /* Button text color */
        border: none;
        border-radius: 50%;
        padding: 10px;
        cursor: pointer;
        box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
        z-index: 1000; /* Ensure it's above other content */
    }

    .scroll-to-top-button i.material-icons {
        font-size: 24px;
    }

    @media only screen and (min-width: 768px) and (max-width: 1023px) {
        li {
            padding-left: 0;
        }
    }
    @media only screen and (max-width: 767px) {
        li {
            padding-left: 0;
        }
    }
</style>
<script>
    export default {
        mounted() {
            // Get the button element by its ID
            const scrollToTopButton = document.getElementById("scrollToTopButton");

            // Add a click event listener to the button
            scrollToTopButton.addEventListener("click", () => {
                // Scroll to the top of the page smoothly
                window.scrollTo({
                    top: 0,
                    behavior: "smooth",
                });
            });

            // Show or hide the button based on the user's scroll position
            window.addEventListener("scroll", () => {
                if (
                    document.body.scrollTop > 20 ||
                    document.documentElement.scrollTop > 20
                ) {
                    scrollToTopButton.style.display = "block";
                } else {
                    scrollToTopButton.style.display = "none";
                }
            });
        },
    };
</script>