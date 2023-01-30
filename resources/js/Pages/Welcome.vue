<script setup>
import { Head } from "@inertiajs/vue3";
defineProps({
    developerName: String,
    frameworks: Array,
});
</script>

<template>
    <div>
        <Head title="Homepage" />
        <h1 class="text-4xl mb-6">Hello {{ developerName }}</h1>
    </div>
</template>
