<template>
    <v-container fluid fill-height class="home-hero" style="max-height: 100vh;">
        <v-layout justify-center align-center column pa-5>
            <div class="display-4 font-weight-black white--text text-xs-center">DES ALIMENTS SAINS</div>
            <div class="display-4 font-weight-black white--text text-xs-center mb-3">POUR VOTRE CORPS</div>
            <div class="display-4 font-weight-bold white--text text-xs-center">
                 <v-text-field
                        label="Entrer un produit"
                        filled
                        rounded
                        dense
                        id="search-bar"
                    ></v-text-field>
            </div>
            <v-btn fab class="mt-5 brown darken-4">
            <v-icon large color="white"></v-icon>
            </v-btn>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    name: 'HomeHero'
};
</script>

<style scoped>
.home-hero {
    background: #ffc107;
    background-size: cover;
    width: 100%;
    height: 100%;
}
#search_bar{
    width:100%;
    color:white
}
</style>