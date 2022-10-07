<template>
  <div class="h-screen"> 
    <div class="min-h-full grid grid-rows-2 grid-cols-1 lg:grid-rows-1 lg:grid-cols-2">
        <div class="relative flex pointer" @click="scrollToElement">
            <img src="https://tailwindui.com/img/ecommerce-images/home-page-02-edition-01.jpg" alt="" class="absolute inset-0 w-full h-full object-center object-cover" />
            <div class="relative w-full flex flex-col items-start justify-end bg-black bg-opacity-40 p-8 sm:p-12">
                <h2 class="uppercase text-2xl font-medium text-white">{{ $t("events.wedding.title") }}</h2>
                <p class="hidden md:block min-h-24 mt-1 font-medium text-white text-opacity-75 text-justify">{{ $t("events.wedding.description1") }}</p>
                <strong class="hidden md:block mt-1 font-medium text-lg text-white text-justify">{{ $t("events.wedding.description2") }}</strong>
                <!-- <a href="#" class="mt-4 text-sm font-medium text-gray-900 bg-white py-2.5 px-4 rounded-md hover:bg-gray-50">Shop now</a> -->
            </div>
        </div>
        <div class="relative flex pointer" @click="scrollToElement">
            <img src="https://tailwindui.com/img/ecommerce-images/home-page-02-edition-02.jpg" alt="" class="absolute inset-0 w-full h-full object-center object-cover group-hover:opacity-75" />
            <div class="relative w-full flex flex-col items-start justify-end bg-black bg-opacity-40 p-8 sm:p-12">
                <h2 class="uppercase text-2xl font-medium text-white">{{ $t("events.seminar.title") }}</h2>
                <p class="hidden md:block min-h-24 mt-1 font-medium text-white text-opacity-75 text-justify">{{ $t("events.seminar.description1") }}</p>
                <strong class="mt-1 font-medium text-lg text-white text-justify">{{ $t("events.seminar.description2") }}</strong>
                <!-- <a href="#" class="mt-4 text-sm font-medium text-gray-900 bg-white py-2.5 px-4 rounded-md hover:bg-gray-50">Shop now</a> -->
            </div>
        </div>
    </div>
  </div>
</template>


<script>
    export default{
        scrollToElement() {
                const el = this.$refs.scrollToMe;
    
                if (el) {
                    // Use el.scrollIntoView() to instantly scroll to the element
                    el.scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            },
    }
    
    </script>
    
    