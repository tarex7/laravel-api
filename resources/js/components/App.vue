.
<template>
    <div class="content">
        <div class="title m-b-md">
            <AppHeader />
        </div>
        <BaseCard v-for="post in posts" :key="post.id" :post="post" />
    </div>
</template>

<script>
import axios from "axios";

import AppHeader from "./AppHeader.vue";
import BaseCard from "./Posts/BaseCard.vue";

export default {
    name: "App",
    components: { AppHeader, BaseCard },
    data() {
        return {
            posts: [],
        };
    },

    methods: {
        fetchPosts() {
            axios.get("/api/posts").then((res) => {
                this.posts = res.data;
            });
        },
    },

    mounted() {
        this.fetchPosts();
    },
};
</script>

<style></style>
