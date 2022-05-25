<template>
    <main class="container_fluid bg_main">
     <section  v-if='!loading'>
            <div class="container w-100">
            <div class="row row-cols-5 p-4 gy-4 h-100">
                <SongList :song= 'album' v-for="(album, index) in albumsSelected" :key="index"/>
            </div>
        </div>
    </section>
    <section v-else>
        <h2>...Caricamento pagina</h2>
    </section>
    </main>
</template>

<script>
import SongList from '@/components/SongListComponent.vue';
import axios from "axios"; 
import state from "@/state";

export default {
     name: "SiteMainComponent",
     components: {
         SongList,
     },
     data () {
         return {
             link: "http://localhost/PHP/esercitazioni-git-php/php-ajax-dischi/milestone-2/src/db.php",
             albums: null,
             loading: true,
        };
     },
     methods: {
     },
     mounted() {
         console.log(axios);
          axios
         .get(this.link)
         .then((response) => {
             console.log(response);
             this.albums = response.data.response;
             this.loading = false;
         })
     },
     computed: {
        albumsSelected(){
            if(state.selectedGenre) {
                    console.log(this.albums);
        return this.albums.filter(album =>{
            return album.genre.toLowerCase().includes(state.selectedGenre.toLowerCase())
         })
            } else {
                return this.albums
            }
        
       }
    }
        
}


</script>

<style lang='scss' scoped>

    .container_fluid {
         min-height: 800px;
        
        h2 {
            text-align: center;
            color: white;
            font-size: 50px;
            padding-top: 100px;
        }
    }

    img {
        aspect-ratio: 1 / 1;
    }

    .card {
        max-height: 400px;
    }

</style>