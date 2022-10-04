.
<template>
    <div class="card w-75 mx-auto my-5">
        <div class="card-body">
            <h5 class="card-title">{{ post.title }}</h5>
            <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
            <p class="card-text">
                {{ post.text }}
            </p>
            <a href="#" class="card-link">Card link</a>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BaseCard',
    props: {
       post: Object
    }
}
</script>

<style></style>
