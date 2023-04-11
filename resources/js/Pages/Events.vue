<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head } from "@inertiajs/vue3";

Echo.channel("trades").listen("NewTrade", (e) => {
    console.log(e.trade);
});
</script>

<template>
    <Head title="Events" />

    <AuthenticatedLayout>
        <template #header>
            <h2
                class="font-semibold text-xl text-gray-800 dark:text-gray-200 leading-tight"
            >
                Events
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="flex flex-wrap">
                    <div class="w-full md:w-2/2 xl:w-3/3 p-3">
                        <div class="bg-white border rounded shadow p-2">
                            <div class="flex flex-row items-center">
                                <div class="flex-shrink pr-4">
                                    <div class="rounded p-3 bg-yellow-600">
                                        <i
                                            class="fas fa-user-plus fa-2x fa-fw fa-inverse"
                                        ></i>
                                    </div>
                                </div>
                                <div class="flex-1 text-right md:text-center">
                                    <h5
                                        class="font-bold uppercase text-gray-500"
                                    >
                                        Latest trade
                                    </h5>
                                    <h3 class="font-bold text-3xl">
                                        <p>
                                            Name:
                                            <span id="latest_trade_user"></span>
                                        </p>
                                    </h3>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
