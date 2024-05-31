<script>
import { store } from '../assets/data/store'
import axios from 'axios'
export default {
    data() {
        return {
            store,
            filmUtente: ''
        };
    },
    methods: {
        filmGen() {
            const options = {
            method: 'GET',
            url: 'https://api.themoviedb.org/3/movie/11?api_key=b7a1e84eb8c806944cebe07238a104c2',
            params: { include_adult: 'false', language: 'en-US', page: '1' },
            headers: {
              accept: 'application/json',
              Authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJiN2ExZTg0ZWI4YzgwNjk0NGNlYmUwNzIzOGExMDRjMiIsInN1YiI6IjY2NTgzOTc4YTlhYWRjMmQzMjJkMjZkMSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5Tg1YJGVZD4xGXXRzegQzbnt5H0vOO5NqWJ_uDG4JRQ'
            }
        };
        axios
            .request(options)
            .then((response) => {
                this.filmUtente = response.data;
            })
            .catch(function (error) {
            console.error(error);
        });
        }
        
    }
}
</script>


<template>
    <section>
        <div class="head">
            <h1>Boolflix</h1>
            <input v-model="filmUtente" type="text" placeholder="Cosa vuoi vedere?">
            <button @click="filmGen()">Cerca Film</button>
        </div>
    </section>
</template>


<style scoped>
.head {
    display: flex;
    padding: 20px;
    align-items: center;
}

.head h1 {
    font-size: 30px;
    margin-right: 30px;
}

.head button {
    background-color: crimson;
    color: black;
    margin-left: 20px;
    padding: 10px 35px;
    font-size: 18px;
    font-weight: 800;
    border: none;
    border-radius: 10px;
    cursor: pointer;
}

.select {
    margin-left: 20px;
    width: 100px;
}
</style>