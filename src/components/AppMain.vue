<script>
import { store } from '../assets/data/store'
export default {
    name: "AppMain",
    data() {
        return {
            store,
        }
    }
}
</script>


<template>
    <section class="bg-crimson">
        <div class="white-container">
            <h3>Trovati {{ store.films.length }} film</h3>
            <!-- <div class="cards-container">
                <div v-for="film in store.films" class="cards">
                    <img src="" alt="">
                    <p class="name">{{ film.title }}</p>
                    <p class="type">{{ film.original_title }}</p>
                    <p class="type">{{ film.original_language }}</p>
                    <p class="type">{{ film.vote_average }}</p>
                </div>
            </div> -->
        </div>
    </section>
</template>


<style scoped>
.bg-crimson {
    background-color: crimson;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
    border-radius: 10px;
}

.white-container {
    width: 80%;
    height: 80%;
    border-radius: 10px;
    background-color: black;
}

h3 {
    background-color: black;
    color: white;
    padding: 20px;
}

/* .cards-container {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
} */


</style>