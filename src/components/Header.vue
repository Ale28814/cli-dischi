<template>
    <section>
        <div class="container h-100">
            <div class="row justify-content-between align-items-center h-100">
                <div class="col-2 h-100">
                    <img src="@/assets/spoty.png" alt="Spotify logo">
                </div>
                <div class="col-4 d-flex">
                    <label for="genre">Type music:</label>
                    <select name="genre" v-model="Genres" @change="$emit('genreSelect', Genres)">
                        <option value="">All</option>
                        <option value="metal">Metal</option>
                        <option value="pop">Pop</option>
                        <option value="rock">Rock</option>
                        <option value="jazz">Jazz</option>
                    </select>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            Genres: '',
        }
    }
}
</script>

<style scoped lang="scss">
section {
    height: 10vh;
    padding: 5px;
    background: #2e3a46;
    
    img {
        border-radius: 50%;
        height: 100%;
    }
    label{
    color: #fff;
    padding-right: 10px;
    }
    select{
    width: 50%;
    }
}

</style>