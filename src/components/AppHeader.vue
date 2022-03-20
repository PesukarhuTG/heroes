<template>
    <nav class="navbar navbar-dark bg-dark">
    <div class="container-fluid">
      <a href="#" class="navbar-brand">{{title}}</a>
      <form class="d-flex">
        <input class="form-control me-2" 
                type="search" 
                placeholder="Поиск..." 
                aria-label="Search" 
                v-model="search"
                @input="changeSearch(search)"
        >
        <button type="reset" class="btn btn-outline-light">
          все
        </button>
      </form>
    </div>
  </nav>
</template>

<script>
    export default {
        name: "AppHeader",
        props: ['title', 'changeSearch'],
        data() {
            return {
              search: '',
            }
        },
    }
</script>

<style scoped>

</style>
