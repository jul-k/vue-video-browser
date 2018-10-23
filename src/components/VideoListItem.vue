<template>
    <li class="list-group-item media">
        <img :src="thumbnailUrl" alt="" class="mr-3">
        <div class="media-body">
            {{ video.snippet.title }}
        </div>
    </li>
</template>

<script>
export default {
    name: "VideoListItem",
    props: {
        video: Object
    },
    computed: {
        thumbnailUrl() {
            return this.video.snippet.thumbnails.default.url;
        }
    }
}
</script>

<style scoped>
    li {
        display: flex;
    }
    li:hover {
        background-color: #eee;
        cursor: pointer;
    }
</style>
