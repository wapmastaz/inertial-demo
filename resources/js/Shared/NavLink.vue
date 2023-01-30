<script setup>
import { Link } from "@inertiajs/vue3";
defineProps({
    active: Boolean,
});
</script>

<template>
    <Link
        class="text-black hover:underline"
        :class="{
            'font-bold text-red-500 underline': active,
        }"
    >
        <slot />
    </Link>
</template>
