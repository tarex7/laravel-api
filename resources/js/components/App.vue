.
<template>
    <div class="content">
        <div class="title m-b-md">
           <AppHeader/>
        </div>
    <BaseCard/>
      
    </div>
</template>

<script>
import axios from 'axios';

import AppHeader from './AppHeader.vue';
import BaseCard from './Posts/BaseCard.vue';

export default {
    name: "App",
    components: { AppHeader, BaseCard },
    data() {
        return {
            posts: [],
        }
    },
    methods: {
        fetchPosts() {
            axios.get("http://127.0.0.1:8000/API/posts").then((res) => {
                this.posts = res.data;
            });
            console.log(this.posts);
        },
        logsomething() {}
    },
    
    mounted() {
        this.fetchPosts;
    },
};
</script>

<style></style>
