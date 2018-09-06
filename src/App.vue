<template>
    <div>
        <SearchBar @termChange="onTermChange">
        </SearchBar>
    </div>
</template>

<script>
import SearchBar from "./components/SearchBar";
const API_KEY = "AIzaSyDXohZgX9DwzAqav0EgYVj5yEU6icq9kSo";

export default {
    name: "App",
    components: {
        SearchBar
    },
    methods: {
        onTermChange(searchTerm) {
            console.log(searchTerm);
        }
    }
}
</script>
