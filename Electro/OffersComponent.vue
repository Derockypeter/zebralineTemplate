<template>
    <div class="container">
        <a href="">
            <div class="bgImg">
                <div class="flex items-center justify-center gap-3 overflow-auto">
                    <div class="flex-shrink-0">
                        <h1>
                            Shop and <strong>save big</strong> on hottest tablets
                        </h1>
                    </div>
                    <div class="flex-shrink-0">
                        <button><em>Starting at</em> <span class="amount"><sup>$</sup>79<sup>99</sup></span></button>
                    </div>
                </div>
            </div>
        </a>
    </div>
</template>
<style scoped>
    .gap-3 {
        gap: 3vh;
    }
    .bgImg {
        background: url("https://transvelo.github.io/electro-html/2.0/assets/img/1400X206/img1.jpg");
        text-transform: uppercase;
        padding: 3.5rem 1.5rem 1.5rem 1.5rem;
        color: #333e48;
    }
    .container {
        width: 85%;
    }
    h1 {
        font-size: 2.00025rem;
        font-weight: 300;
        margin: 0;
    }
    button {
        padding: 0.5rem 2.5rem;
        text-transform: uppercase;
        border-radius: 0.4375rem !important;
        background-color: var(--primary-color);
        border: none;
        font-family: "Open Sans", Helvetica, Arial, sans-serif;
    }
    button em {
        display: block;
        font-size: 0.875rem;
        font-weight: 300;
    }
    strong {
        font-weight: 700;
    }
    .amount {
        font-size: 1.87512rem;
        font-weight: 700;
    }
    sup {
        font-size: 60%;
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