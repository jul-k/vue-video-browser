<template>
    <div v-if="video">
        <div>
            <iframe :src="videoUrl" frameborder="0"></iframe>
        </div>
        <div class="details">
            <h4>{{ video.snippet.title }}</h4>
            <p>{{ video.snippet.description }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "VideoDetail",
    props: {
        video: Object
    },
    computed: {
        videoUrl() {
            // const videoId = this.video.id.videoId;
            const { videoId } = this.video.id; // ES6 syntax
            return `http://www.youtube.com/embed/${videoId}`;
        }
    }
}
</script>

<style scoped>
    .details {
        margin-top: 10px;
        padding: 10px;
        border: 1px solid #000;
        border-radius: 4px;
    }
</style>