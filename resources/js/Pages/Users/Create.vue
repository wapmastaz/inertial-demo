<script setup>
import { Head, useForm } from "@inertiajs/vue3";

const form = useForm({
    name: null,
    email: null,
    password: null,
});

const createUser = () => {
    form.post("/users/store");
};
</script>

<template>
    <div>
        <Head title="Create New User" />
        <h1 class="text-3xl">Create New User</h1>
        <form
            @submit.prevent="createUser"
            class="mt-10 max-w-md mx-auto"
            autocomplete="false"
        >
            <div class="mb-6">
                <label for="name" class="mb-1 flex uppercase">Name</label>
                <input
                    type="text"
                    class="px-2 py-3 flex w-full border rounded-md"
                    autofocus
                    v-model="form.name"
                />
                <span
                    class="text-sm mt-2 text-red-500"
                    v-if="form.errors.name"
                    >{{ form.errors.name }}</span
                >
            </div>
            <div class="mb-6">
                <label for="email" class="mb-1 flex uppercase">Email</label>
                <input
                    type="email"
                    class="px-2 py-3 flex w-full border border-gray-400 rounded-md"
                    v-model="form.email"
                />
                <span
                    class="text-sm mt-2 text-red-500"
                    v-if="form.errors.email"
                    >{{ form.errors.email }}</span
                >
            </div>
            <div class="mb-6">
                <label for="password" class="mb-1 flex uppercase"
                    >Password</label
                >
                <input
                    type="password"
                    class="px-2 py-3 flex w-full border rounded-md"
                    v-model="form.password"
                />
                <span
                    class="text-sm mt-2 text-red-500"
                    v-if="form.errors.password"
                    >{{ form.errors.password }}</span
                >
            </div>
            <div class="mb-6">
                <button
                    type="submit"
                    class="bg-teal-500 text-white px-6 py-3 rounded-lg"
                    :disabled="form.processing"
                >
                    Submit
                </button>
            </div>
        </form>
    </div>
</template>
