<template>
    <div id="app">

        <app-header/>

        <div class="container">
            <h1 class="pt-3 pb-3">Персонажи Marvel</h1>
            
            <app-modal/>

            <spinner/>

            <div class="row">
                <div v-for="(el, idx) in characters" :key="el.id" class="card mb-3" style="max-width: 540px;">
                  <div class="row g-0">
                    <div class="col-md-4">
                      <img :src="el.thumbnail" class="img-fluid rounded-start" :alt="el.name">
                    </div>
                    <div class="col-md-8">
                      <div class="card-body">
                        <h5 class="card-title">{{el.name}}</h5>
                        <button type="button" class="btn btn-secondary" data-bs-toggle="modal" data-bs-target="#exampleModal"
                                @click="characterIndex = idx">
                          Подробнее
                        </button>
                      </div>
                    </div>
                  </div>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
    import Spinner from "./components/Spinner";
    import AppModal from "./components/AppModal";
    import AppHeader from "./components/AppHeader";

    export default {
        name: 'App',
        components: {
            AppHeader,
            AppModal,
            Spinner,
        },
        data() {
            return {
                loading: false,
                characters: [],
                characterIndex: 0,
            }
        },
        methods: {
            fetchCharacters: function() {
                return fetch('https://netology-api-marvel.herokuapp.com/characters')
                    .then(res => res.json())
                    .then(data => this.characters = data)
            },

        },

        computed: {},
        mounted() {
            this.fetchCharacters();
          },
    }
</script>

<style>

</style>
