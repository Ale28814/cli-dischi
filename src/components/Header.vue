<template>
    <section>
        <div class="container">
            <div class="row ">
                <div class="">
                    <img src="@/assets/spoty.png" alt="Spotify logo">
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped lang="scss">
section {
    height: 10vh;
    padding: 5px;
    background: #2e3a46;
    
    img {
        height: 90px;
    }
}
</style>