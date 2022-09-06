<template>
<main class="bg-white">
    <section class="relative flex items-center justify-center overflow-hidden h-screen">
        <div class="mt-10 z-30 lg:max-w-7xl lg:mx-auto lg:px-8 w-screen mx-auto" data-aos="fade-down" data-aos-anchor-placement="top">
            <h1 class="text-center lg:text-left uppercase mt-0 text-3xl font-extrabold tracking-tight text-white md:text-5xl lg:text-6xl">{{ $t("home.title1") }} <br>{{ $t("home.title2") }} <br> {{ $t("home.title3") }}</h1>
            <!-- CAROUSEL-->
            <div id="carouselServicesCaptions" class="h_main_carousel carousel slide" data-bs-ride="carousel">
                <div class="carousel-inner w-2/3 overflow-hidden flex">
                    <div class="carousel-item active w-full">
                        <div class="carousel-caption hidden md:block text-white">
                            <p class="text-xl">{{ $t("home.subtitle1") }}</p>
                        </div>
                    </div>
                    <div class="carousel-item w-full">
                        <div class="carousel-caption hidden md:block text-white">
                            <p class="text-xl">{{ $t("home.subtitle2") }}</p>
                        </div>
                    </div>
                    <div class="carousel-item w-full">
                        <div class="carousel-caption hidden md:block text-white">
                            <p class="text-xl">{{ $t("home.subtitle3") }}</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="w-32 mx-auto mt-2 lg:mx-0">
                <router-link to="/booking" class=" custom-border-btn mt-0 p-2 sm:mt-5 block font-light text-white text-center text-xl">{{ $t("home.button") }}</router-link>
            </div>
        </div>

        <video autoplay loop muted class="video_home absolute top-0 z-10 w-full">
            <source src="https://assets.mixkit.co/videos/preview/mixkit-set-of-plateaus-seen-from-the-heights-in-a-sunset-26070-large.mp4" type="video/mp4" />
            Your browser does not support the video tag.
        </video>
        <img class="absolute w-full md:hidden" src="img/servicesCategory.jpeg" alt="pool" style="height:450px; filter: brightness(0.8);">

    </section>

    <section class="md:pt-16 pt-16 lg:max-w-7xl lg:mx-auto  lg:px-8">
        <div class="">
            <div class="md:mb-8 mb-0 px-4 w-full mx-auto text-center sm:px-6 lg:px-0">
                <h2 style="font-size: 1.5em;">{{ $t("home.description") }}</h2>
            </div>
            <!-- Category section -->
            <div class="p_xs_img" aria-labelledby="category-heading" data-aos="fade-up" data-aos-anchor-placement="top-bottom">

                <div class="mt-6 grid grid-cols-1 gap-y-6 sm:grid-cols-2 sm:grid-rows-2 sm:gap-x-6 lg:gap-8 sm:px-5">
                    <div class="group aspect-w-2 md:aspect-h-1 sm:aspect-h-1 aspect-h-2 overflow-hidden sm:aspect-h-1 sm:aspect-w-1 sm:row-span-2">
                        <img src="img/servicesCategory.jpeg" alt="" class="object-center absolute z-1 object-cover group-hover:opacity-75" />
                        <!-- <div aria-hidden="true" class="bg-gradient-to-b from-transparent to-black opacity-30" /> -->
                        <div class="p-6 flex absolute z-30 items-end">
                            <div>
                                <h3 class="font-semibold text-white">
                                    <a href="/services">
                                        <span class="absolute inset-0" />
                                        {{ $t("home.category.services.title") }}
                                    </a>
                                </h3>
                                <p aria-hidden="true" class="mt-1 text-sm text-white">{{ $t("home.category.services.description") }}</p>
                            </div>
                        </div>
                    </div>
                    <div class="group aspect-w-2 md:aspect-h-1 sm:aspect-h-1 aspect-h-2 overflow-hidden sm:relative sm:aspect-none sm:h-full">
                        <img src="img/roomsCategory.jpeg" alt="" class="object-center object-cover group-hover:opacity-75 absolute sm:inset-0 sm:w-full sm:h-full" />
                        <div aria-hidden="true" class="bg-gradient-to-b from-transparent to-black opacity-50 sm:absolute sm:inset-0" />
                        <div class="p-6 flex items-end sm:absolute sm:inset-0">
                            <div>
                                <h3 class="font-semibold text-white">
                                    <a href="/rooms">
                                        <span class="absolute inset-0" />
                                        {{ $t("home.category.rooms.title") }}
                                    </a>
                                </h3>
                                <p aria-hidden="true" class="mt-1 text-sm text-white">{{ $t("home.category.rooms.description") }}</p>
                            </div>
                        </div>
                    </div>
                    <div class="group aspect-w-2 md:aspect-h-1 sm:aspect-h-1 aspect-h-2 overflow-hidden sm:relative sm:aspect-none sm:h-full">
                        <img src="img/eventsCategory.jpeg" alt="" class="object-center object-cover group-hover:opacity-75 absolute sm:inset-0 sm:w-full sm:h-full" />
                        <div aria-hidden="true" class="bg-gradient-to-b from-transparent to-black opacity-50 sm:absolute sm:inset-0" />
                        <div class="p-6 flex items-end sm:absolute sm:inset-0">
                            <div>
                                <h3 class="font-semibold text-white">
                                    <a href="/events">
                                        <span class="absolute inset-0" />
                                        {{ $t("home.category.events.title") }}
                                    </a>
                                </h3>
                                <p aria-hidden="true" class="mt-1 text-sm text-white">{{ $t("home.category.events.description") }}</p>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </section>

    <!-- PHILOSOPHY -->
    <section class="py-16 relative bg-white overflow-hidden">
        <div>
            <div class="relative" data-aos="fade-up" data-aos-anchor-placement="top-bottom">
                <div class="lg:mx-auto lg:max-w-7xl lg:px-8 lg:grid lg:grid-cols-2 lg:grid-flow-col-dense lg:gap-24">
                    <div class="px-4 max-w-3xl mx-auto s lg:py-16 lg:max-w-none lg:mx-0 lg:px-0">
                        <div>
                            <div class="">
                                <h2 class="text-3xl font-extrabold tracking-tight text-gray-900">{{ $t("home.philosophy.title") }}</h2>
                                <p class="mt-4 text-lg text-gray-500">{{ $t("home.philosophy.description1") }}</p>
                                <p class="mt-4 text-lg text-gray-500">{{ $t("home.philosophy.description2") }}</p>

                            </div>
                        </div>

                    </div>
                    <div class="mt-7 sm:mt-7 lg:mt-0">
                        <div class="md:pl-4 px-4 lg:px-0 lg:m-0 lg:relative lg:h-full">
                            <img class="md:w-full sm:w-full  object-cover shadow-xl lg:absolute lg:left-0 lg:h-full lg:w-auto" src="img/domaine_complet.webp" alt="Inbox user interface" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <div class="relative overflow-hidden">
        <!-- Decorative background image and gradient -->
        <div aria-hidden="true" class="absolute inset-0">
            <div class="absolute inset-0 max-w-7xl mx-auto overflow-hidden xl:px-8">
                <img src="https://tailwindui.com/img/ecommerce-images/home-page-02-sale-full-width.jpg" alt="" class="w-full h-full object-center object-cover" />
            </div>
            <div class="absolute inset-0 bg-white bg-opacity-75" />
            <div class="absolute inset-0 bg-gradient-to-t from-white via-white" />
        </div>

    </div>
</main>
</template>

<script>
import {
    ref
} from 'vue';
import 'tw-elements';

export default {
    components: {},

    setup() {
        const mobileMenuOpen = ref(false)

        return {
            mobileMenuOpen,
        }
    },
}
</script>

<style>
.custom-border-btn {
    border: 1px white solid;
}

.custom-border-btn:hover {
    background: white;
    color: #101010;
}

.p_xs_img img {
    filter: brightness(0.8);
}

@media all and (max-width:1023px) {
    .h_main_carousel {
        text-align: center;
    }

    .h_main_carousel .carousel-inner {
        margin: 0 auto;
    }
}

@media all and (max-width:767px) {
    .video_home {
        display: none;
    }

    .h_main_carousel {
        display: none
    }
}

@media all and (max-width:639px) {
    .p_xs_img {
        padding: 0 18px 0 18px;
    }
}
</style>
