.
<template>
   <div id="home-page">
    <BaseCard v-for="post in posts" :key="post.id" :post="post" />
   </div>
</template>

<script>
import BaseCard from '../Posts/BaseCard.vue';
export default {
    name: "HoemPage",
    components: { BaseCard },
    props: {
        posts: Array
    }
};
</script>

