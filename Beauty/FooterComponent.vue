<template>
    <div>
        <div class="footer">
            <div class="footer-img">
                <!-- <img
                    src="https://websitedemos.net/organic-shop-02/wp-content/uploads/sites/465/2019/07/organic-store-white-logo.png"
                    alt="img"
                    class="img-footer"
                /> -->
                {{ brandname }}
                <p class="footer-text">
                    Maecenas mi justo, interdum at consectetur vel,
                    <br />tristique et arcu. Ut quis eros blandit, ultrices diam
                    in, <br />
                    elementum ex. Suspendisse quis faucibus urna. <br />
                    Suspendisse pellentesque.
                </p>
            </div>

            <div class="footer-links">
                <h4 class="footer-link">Quick Links</h4>

                <ul>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Cart</a></li>
                    <li><a href="#">Checkout</a></li>
                    <li><a href="#">Contact</a></li>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">My account</a></li>
                    <li><a href="#">Shop</a></li>
                </ul>
            </div>

            <div class="footer-message">
                <h6 class="footer-title">Download our App</h6>

                <p class="footer-msg">
                    Lorem ipsum dolor sit amet, <br />
                    consectetur adipiscing elit. Donec <br />
                    aliquam gravida sollicitudin. Praesent <br />
                    porta enim mi, non tincidunt libero <br />
                    interdum sit amet.
                </p>
            </div>
        </div>

        <div class="footer-two">
            <div class="foot-two-text">
                <p class="footer-copy">Copyright © 2023 | {{ brandname }}</p>
            </div>
            <div class="footer-socials">
                <i class="fa-brands fa-facebook"></i>
                <i class="fa-brands fa-twitter"></i>
                <i class="fa-brands fa-instagram"></i>
            </div>
        </div>
    </div>
</template>
<style scoped>
    .footer {
        background-color: rgb(0, 21, 36);
        color: white;
        display: flex;
        padding: 5vw;
        justify-content: space-between;
        gap: 5vw;
    }

    .footer-img {
        display: block;
        justify-content: space-between;
        gap: 2vw;
    }

    .img-footer {
        width: 40%;
    }

    .footer-text {
        margin-top: 6%;
        color: rgb(167, 174, 179);
        font-family: "Open Sans", sans-serif;
    }

    .footer-link {
        font-family: "Merriweather", serif;
        font-size: 150%;
    }

    ul,
    li,
    a {
        color: white;
    }

    .footer-links {
        color: white;
    }

    .footer-two {
        background-color: rgb(0, 21, 36);
        color: white;
        display: flex;
        align-items: center;
        padding: 4vw;
        justify-content: space-between;
    }

    .foot-two-text {
        margin-left: 3vw;
    }

    .footer-socials {
        margin-right: 5vw;
        display: flex;
        justify-content: space-between;
        gap: 2vw;
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