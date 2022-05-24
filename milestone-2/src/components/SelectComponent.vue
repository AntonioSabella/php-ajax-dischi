<template>
     <div class="d-flex w-50 align-items-center justify-content-around">
            <label class="me-2 text-uppercase text-white w-50" for="genere">Seleziona genere :</label>
            <select  
                @change="$emit('changeSelect')"
                @input="$emit('input', $event.target.value)" class="form-select bg_main w-70 h-50 text-white me-3" name="genere" id="genere">
                <option selected disabled>Generi Musicali</option>
                <option class="bg_header" value="">All</option>
                <option class="bg_header" value="Pop">Pop</option>
                <option class="bg_header" value="Jazz">Jazz</option>
                <option class="bg_header" value="Metal">Metal</option>
                <option class="bg_header" value="Rock">Rock</option>
            </select>
        </div>

</template>

<script>
export default {
    name: "SelectComponent",
    props: {
        selectedGenre: String 
    },
}
</script>

<style lang='scss' scoped>

</style>