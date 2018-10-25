<template>
    <div>
        <input type="text" @input="onInput" placeholder="start typing here...">
    </div>
</template>

<script>
export default {
    name: "SearchBar",
    methods: {
        onInput: function(event) {
            this.$emit("termChange", event.target.value);
        }
    }
}
</script>

<style scoped>
    input {
        width: 75%;
        outline: 0;
    }
    div {
        text-align: center;
        margin: 20px;
    }
</style>
