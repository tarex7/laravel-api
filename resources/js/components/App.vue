.
<template>
    <div class="content">
        <div class="title m-b-md">
            <AppHeader />
        </div>
        <HomePage :posts="posts" />
    </div>
</template>

<script>
import axios from "axios";

import AppHeader from "./AppHeader.vue";
import BaseCard from "./Posts/BaseCard.vue";
import HomePage from "./Pages/HomePage.vue";

export default {
    name: "App",
    components: { AppHeader, BaseCard, HomePage },
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
