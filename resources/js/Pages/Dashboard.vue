<script setup>
import Admin from '@/Layouts/Admin.vue';
import {Head} from '@inertiajs/vue3';
</script>

<template>
    <Head title="Dashboard"/>

    <Admin>
        <div class="card">
            <div class="card-body">You're logged in!</div>
        </div>
    </Admin>
</template>
