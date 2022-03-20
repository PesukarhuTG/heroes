<template>
    <div class="text-center">
        <div class="spinner-grow text-danger" role="status">
            <span class="visually-hidden">Loading...</span>
        </div>
        <div class="spinner-grow text-danger" role="status">
            <span class="visually-hidden">Loading...</span>
        </div>
        <div class="spinner-grow text-danger" role="status">
            <span class="visually-hidden">Loading...</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Spinner"
    }
</script>

<style scoped>
  .spinner-grow {
    margin: 0 10px;
  }
</style>
