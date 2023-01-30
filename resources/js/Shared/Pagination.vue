<script setup>
import { Link } from "@inertiajs/vue3";
defineProps({
    links: Array,
});
</script>

<template>
    <div>
        <nav
            class="flex flex-row flex-nowrap justify-between md:justify-center items-center"
        >
            <template v-for="link in links" :key="link.label">
                <Link
                    class="flex w-10 h-10 mr-1 justify-center items-center rounded-full border border-gray-200 bg-white hover:border-gray-300"
                    :class="{ 'bg-black text-white ': link.active }"
                    :href="link.url"
                    v-if="link.url"
                    :title="`Page ${link.label}`"
                >
                    <span v-html="link.label"></span>
                </Link>
                <span class="mx-2" v-else v-html="link.label"></span>
            </template>

            <!-- <a
                class="hidden md:flex w-10 h-10 mx-1 justify-center items-center rounded-full border border-gray-200 bg-white text-black hover:border-gray-300"
                href="#"
                title="Page 1"
            >                    <span class="sr-only" v-if="link.url">Previous Page</span>
                    <svg
                        class="block w-4 h-4 fill-current"
                        viewBox="0 0 256 512"
                        aria-hidden="true"
                        role="presentation"
                    >
                        <path
                            d="M238.475 475.535l7.071-7.07c4.686-4.686 4.686-12.284 0-16.971L50.053 256 245.546 60.506c4.686-4.686 4.686-12.284 0-16.971l-7.071-7.07c-4.686-4.686-12.284-4.686-16.97 0L10.454 247.515c-4.686 4.686-4.686 12.284 0 16.971l211.051 211.05c4.686 4.686 12.284 4.686 16.97-.001z"
                        ></path>
                    </svg>
                1
            </a>
            <a
                class="hidden md:flex w-10 h-10 mx-1 justify-center items-center rounded-full border border-gray-200 bg-white text-black hover:border-gray-300"
                href="#"
                title="Page 2"
            >
                2
            </a>
            <a
                class="hidden md:flex w-10 h-10 mx-1 justify-center items-center rounded-full border border-black bg-black text-white pointer-events-none"
                href="#"
                aria-current="page"
                title="Page 3"
            >
                3
            </a>
            <a
                class="hidden md:flex w-10 h-10 mx-1 justify-center items-center rounded-full border border-gray-200 bg-white text-black hover:border-gray-300"
                href="#"
                title="Page 4"
            >
                4
            </a>
            <a
                class="hidden md:flex w-10 h-10 mx-1 justify-center items-center rounded-full border border-gray-200 bg-white text-black hover:border-gray-300"
                href="#"
                title="Page 5"
            >
                5
            </a>
            <a
                class="flex w-10 h-10 ml-1 justify-center items-center rounded-full border border-gray-200 bg-white text-black hover:border-gray-300"
                href="#"
                title="Next Page"
            >
                <span class="sr-only">Next Page</span>
                <svg
                    class="block w-4 h-4 fill-current"
                    viewBox="0 0 256 512"
                    aria-hidden="true"
                    role="presentation"
                >
                    <path
                        d="M17.525 36.465l-7.071 7.07c-4.686 4.686-4.686 12.284 0 16.971L205.947 256 10.454 451.494c-4.686 4.686-4.686 12.284 0 16.971l7.071 7.07c4.686 4.686 12.284 4.686 16.97 0l211.051-211.05c4.686-4.686 4.686-12.284 0-16.971L34.495 36.465c-4.686-4.687-12.284-4.687-16.97 0z"
                    ></path>
                </svg>
            </a> -->
        </nav>
    </div>
</template>
