<template>
    <div>
        <SearchBar @termChange="onTermChange">
        </SearchBar>
        <VideoList></VideoList>
        {{ videos.length }}
    </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
const API_KEY = "AIzaSyDXohZgX9DwzAqav0EgYVj5yEU6icq9kSo";

export default {
    name: "App",
    components: {
        SearchBar,
        VideoList
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
        }
    }
}
</script>
