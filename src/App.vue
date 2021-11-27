<template>
    <div id="app">
        <!-- HEADER -->
        <Header @genreSelect="genreChosen"/>

        <!-- MAIN -->
        <main>
            <Album :Albums="filterGenres" />
        </main>
    </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import Album from '@/components/Album.vue';
export default {
  name: 'App',
  components: {
    Header,
    Album,
  },
  data() {
        return {
            albumCollection: null,
            Genres: '',
        };
    },
    computed: {
        filterGenres() {
            if(this.Genres === '') {
                return this.albumCollection;
            }
            return this.albumCollection.filter(item => {
                return item.genre.toLowerCase().includes(this.Genres)
            });
        }
    },
    created() {
        this.getAlbum();
    },
    methods: {
        getAlbum() {
            /* Call API */
            axios
                .get('https://flynn.boolean.careers/exercises/api/array/music')
                .then(result => {
                    this.albumCollection = result.data.response;
                })
                .catch(error => console.log(error));
        },
        genreChosen(genre) {
            this.Genres = genre;
        }
    }
}
</script>
<style lang="scss">
@import '@/styles/glob.scss';
</style>
