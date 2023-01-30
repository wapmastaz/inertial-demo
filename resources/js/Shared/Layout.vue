<script setup>
import Nav from "@/Shared/Nav.vue";
import NavLink from "@/Shared/NavLink.vue";
import { usePage } from "@inertiajs/vue3";
import { computed } from "@vue/runtime-core";

const username = computed(() => {
    return usePage().props.auth.username;
});
</script>
<template>
    <section class="bg-gray-200 p-4">
        <header class="flex justify-between">
            <div class="flex items-center">
                <h1 class="font-bold text-lg mb-0 text-black">
                    <NavLink href="/" class="text-black">App Name</NavLink>
                </h1>
                <p class="mb-0 text-sm ml-4">Welcome Back, {{ username }}!</p>
            </div>

            <Nav />
        </header>
    </section>
    <section class="max-w-2xl mx-auto mt-10">
        <slot />
    </section>
</template>
