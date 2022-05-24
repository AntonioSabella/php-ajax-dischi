<template>
    <div class="col d-flex align-items-center text-center h-100">
        <div class="card bg_header p-3">
            <img class="img-fluid" :src="song.poster" alt="">
            <div class="album_title">
                <h6 class="text-white mt-3 lh-0">{{song.title}}</h6>
            </div>
            <p class="text-muted m-0">{{song.author}}</p>
            <p class="text-muted m-0">{{song.year}}</p>
         </div>
    </div>
</template>

<script>
export default {
    name:'SongList',
    props:{
        song: Object
    }
};
</script>

<style lang='scss' scoped>
 .container_fluid {
        height: calc(100% - 80px);
        h2 {
            text-align: center;
            color: white;
        }
    }
    img {
        aspect-ratio: 1 / 1;
    }

    .card {
        max-height: 400px;
        .album_title {
            height: 60px;
        }
    }
</style>