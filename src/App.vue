<template>
    <div id="app">

        <app-header title="Marvel" :changeSearch="changeSearch" />

        <div class="container">
            <h1 class="pt-3 pb-3">Персонажи Marvel</h1>

            <h5 v-if="!searchCharacters.length">К сожалению, по вашему запросу ' {{search}} ' ничего не найдено</h5>

            <app-modal :character="searchCharacters[characterIndex]" />

            <spinner v-if="loading" />

            <div class="row">
                <div v-for="(el, idx) in searchCharacters" 
                    class="card mb-3" 
                    :key="el.id" 
                    style="max-width: 540px;">
                  <div class="row g-0">
                    <div class="col-md-4">
                      <img :src="el.thumbnail" class="img-fluid rounded-start" :alt="el.name">
                    </div>
                    <div class="col-md-8">
                      <div class="card-body">
                        <h5 class="card-title">{{el.name}}</h5>

                        <button type="button" 
                                class="btn btn-secondary" 
                                data-bs-toggle="modal" 
                                data-bs-target="#exampleModal"
                                @click="characterIndex = idx"
                        >
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
                search: '',
            }
        },
        methods: {
          fetchCharacters: function() {
            return fetch('https://netology-api-marvel.herokuapp.com/characters')
              .then(res => res.json()) //то, что получим, преобразуется в json
              .then(data => this.characters = data) //нужно куда-то записать полученную информацию
          },
          changeSearch: function(value) {
            this.search = value
          }
        },
        //для предвариательной обработки данных
        computed: {
          searchCharacters: function() {
            const {search, characters} = this
            return characters.filter(item => {
              return item.name.toLowerCase().indexOf(search.toLowerCase()) !== -1
            })
          },
        },
        //спец метод жизненного цикла, ктр-й срабатывает тогда, когда наш компонент оказался на странице
        async mounted(){
          this.loading = true
          await this.fetchCharacters()
          this.loading = false
        },
    }
</script>

<style>

</style>
