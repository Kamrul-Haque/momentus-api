<script setup>
import SideNavLink from "@/Components/SideNavLink.vue";
import {usePage} from "@inertiajs/vue3";

const props = defineProps({
    showSideBar: {
        type: Boolean
    }
});

const page = usePage();
</script>

<template>
    <SideNavLink :href="route('dashboard')"
                 :active="route().current('dashboard')">
        <span class="mdi mdi-view-dashboard"></span>
        <span :class="[showSideBar ? 'pl-3' : 'md:hidden']">Dashboard</span>
    </SideNavLink>
    <SideNavLink v-if="page.props.auth.user.role === 1"
                 :href="route('settings.edit', page.props.settings.id)"
                 :active="route().current('settings.*')">
        <span class="mdi mdi-cog"></span>
        <span :class="[showSideBar ? 'pl-3' : 'md:hidden']">Settings</span>
    </SideNavLink>
</template>
