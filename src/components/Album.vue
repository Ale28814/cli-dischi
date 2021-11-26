<template>
    <section class="container">
        <div class=""
        v-if="albumCollection != null">

            <div class="album"
            v-for="(element, index) in albumCollection" :key="`Album-${index}`">
                <CardAlbum
                    :Image="element.poster"
                    :MainTitle="element.title"
                    :Author="element.author"
                    :Text1="element.year"
                    :Text2="element.genre"
                />
            </div>

        </div>

            <Loading v-else />
    </section>
</template>

<script>
import axios from 'axios';
import CardAlbum from '@/components/CardAlbum.vue';
import Loading from '@/components/Loading.vue';
export default {
    name: 'AlbumSection',
    components: {
        CardAlbum,
        Loading,
    },
    data() {
        return {
            albumCollection: null,
        };
    },
    created() {
        this.getAlbum();
    },
    methods: {
        getAlbum() {
            /* Call API for data */
            axios
                .get('https://flynn.boolean.careers/exercises/api/array/music')
                .then(result => {
                    this.albumCollection = result.data.response;
                })
                .catch(error => console.log(error));
        }
    }
}
</script>

<style scoped lang="scss">
    section {
        text-align: center;
        padding: 3.5rem 1.5rem;
        color: #fff;
    }
    .album {
        width: calc(100% / 8);
        padding: 7px;
    }
</style>