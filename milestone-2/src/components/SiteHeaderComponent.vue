<template>
   <header id="site_header" class="container_fluid bg_header d-flex justify-content-between align-items-center">
        <div class="logo_box">
                <img src="https://www.freepnglogos.com/uploads/spotify-logo-png/spotify-download-logo-30.png" alt="">   
        </div>
        <SelectComponent v-model="selectedGenre" @changeSelect="select" />
       
   
    </header> 
</template>

<script>
import SelectComponent from '@/components/SelectComponent.vue'
import state from '@/state.js';
export default {
    name: 'SiteHeaderComponent',
    components: {
        SelectComponent,
    },
    data () {
        return {
            selectedGenre: ''
        }
    },
    methods: {
        select() {
            //console.log(this.select);
            //console.log(state);
            state.selectedGenre = this.selectedGenre
        }
    }
}
</script>

<style lang='scss' scoped>
 #site_header {
    height: 100px;
    padding-bottom: 1rem; 
 }

 .logo_box {
     padding: 0.5rem 1.5rem;
     img {
         width: 50px;
         aspect-ratio: 1/1;
     }
 }
</style>
