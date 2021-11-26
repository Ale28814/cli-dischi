<template>
    <div id="app">
        <!-- HEADER -->
        <Header />

        <!-- MAIN -->
        <main>
            <Album />
        </main>
    </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Album from '@/components/Album.vue';
export default {
  name: 'App',
  components: {
    Header,
    Album,
  }
}
</script>
<style lang="scss">
</style>
