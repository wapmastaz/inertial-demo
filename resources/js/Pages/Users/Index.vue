<script setup>
import { Link, Head, router } from "@inertiajs/vue3";
import Pagination from "@/Shared/Pagination.vue";
import { ref } from "@vue/reactivity";
import { watch } from "@vue/runtime-core";
// import { Inertial } from "Inet";
defineProps({
    time: String,
    users: Object,
});

let search = ref("");

watch(search, (value) => {
    router.get("/users/", { search: value });
});
</script>
<template>
    <Head title="Users" />

    <section class="">
        <div class="mb-6 flex justify-between">
            <h1 class="text-3xl">Users</h1>

            <input
                type="text"
                v-model="search"
                class="px-2 border rounded-lg"
                placeholder="search..."
            />
        </div>
        <div class="flex items-center justify-end mb-4">
            <Link
                href="/users/create"
                class="bg-teal-500 text-white px-3 py-2 rounded-lg ml-5"
                >Create New</Link
            >
        </div>

        <table class="w-full mx-auto border text-sm">
            <thead
                class="bg-gray-800 text-xs uppercase text-gray-100 font-medium"
            >
                <tr>
                    <th>#</th>
                    <th scope="col" class="px-6 py-3 text-left tracking-wider">
                        Name
                    </th>
                    <th scope="col" class="px-6 py-3 text-left tracking-wider">
                        Email
                    </th>
                </tr>
            </thead>
            <tbody class="">
                <tr class="" v-for="user in users.data" :key="user.id">
                    <td class="pl-4">{{ user.id }}</td>
                    <td class="flex px-6 py-4 whitespace-nowrap">
                        <span class="ml-2 font-medium">{{ user.name }}</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                        {{ user.email }}
                    </td>
                </tr>
            </tbody>
        </table>

        <section class="mt-6">
            <Pagination :links="users.links" />
        </section>
        <p>The current time is {{ time }}</p>
        <Link class="text-blue-500" href="/users" preserve-scroll>refresh</Link>
    </section>
</template>
