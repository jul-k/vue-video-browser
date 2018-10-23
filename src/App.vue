<template>
    <div class="container">
        <SearchBar @termChange="onTermChange">
        </SearchBar>
        <VideoDetail :video=""></VideoDetail>
        <VideoList 
            :videos="videos"
            @videoSelect="onVideoSelect"
        >
        </VideoList>
    </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";

const API_KEY = "AIzaSyDXohZgX9DwzAqav0EgYVj5yEU6icq9kSo";

export default {
    name: "App",
    components: {
        SearchBar,
        VideoList,
        VideoDetail
    },
    data() {
        return {
            videos: []
        }
    },
    methods: {
        onTermChange(searchTerm) {
            axios.get("https://www.googleapis.com/youtube/v3/search", {
                params: {
                    key: API_KEY,
                    type: "video",
                    part: "snippet",
                    q: searchTerm
                }
            }).then(res => {
                this.videos = res.data.items;
            });
        },
        onVideoSelect(video) {
            console.log(video);
        }
    }
}
</script>
