<template>
    <span><img class="nav-icon" src="@/assets/image/data.png" /></span>
    &ensp;
    <hr />
    &ensp;
    <router-link class="nav-router-item" v-for="(item, index) in menuLinks" :key="index" :to="item.path">
        <span class="nav-tag" :class="item.icon">&ensp; {{ t(item.text) }}
        </span>
    </router-link>
</template>

<script setup lang="ts">
import { useI18n } from "vue-i18n";

const { t } = useI18n();

interface RouteLinks {
    path: string;
    icon: string;
    text: string;
}

const menuLinks: RouteLinks[] = [
    {
        path: "/",
        icon: "iconfont icon-home",
        text: "home",
    },
    {
        path: "/data",
        icon: "iconfont icon-data",
        text: "data",
    },
    {
        path: "/model",
        icon: "iconfont icon-model",
        text: "model",
    },
    {
        path: "/visualization",
        icon: "iconfont icon-visualization",
        text: "visualization",
    },
    {
        path: "/about",
        icon: "iconfont icon-about-us",
        text: "about",
    },
];
</script>

<style>
.nav-router-item {
    margin: 0 10px;
    height: fit-content;
    user-select: none;
}

.nav-icon {
    max-height: 32px;
}

</style>