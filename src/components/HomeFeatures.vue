<template>
    <v-container grid-list-lg>
        <v-layout row>
            <v-flex center class="display-2 text-xs-center my-5">Features</v-flex>
        </v-layout>
        <v-layout row wrap>
            <v-flex xs12 sm12 md4>
                <v-card
                    class="mx-auto my-12"
                    max-width="374">
                    <template slot="progress">
                    <v-progress-linear
                        color="deep-purple"
                        height="10"
                        indeterminate
                    ></v-progress-linear>
                    </template>

                    <v-img
                    height="250"
                    src="../assets/icons/bibliotheque.jpg"
                    ></v-img>

                    <v-card-title>Bibliothèque nutritionnelle</v-card-title>

                    <v-card-text>
                  
                    <div>KenkoApp vous fournis les informations nutritionnelle de vos produits.</div>
                    </v-card-text>
                </v-card>
            </v-flex>
            <v-flex xs12 sm12 md4>
                <v-card
                    class="mx-auto my-12"
                    max-width="374">
                    <template slot="progress">
                    <v-progress-linear
                        color="deep-purple"
                        height="10"
                        indeterminate
                    ></v-progress-linear>
                    </template>

                    <v-img
                    height="250"
                    src="../assets/icons/guide.jpg"
                    ></v-img>

                    <v-card-title>Guide nutritionnelle</v-card-title>

                    <v-card-text>
                  
                    <div>KenkoApp vous fournis un guide nutritionnelle afin d'adapté au mieu votre alimentation selon votre régime.</div>
                    </v-card-text>
                </v-card>
            </v-flex>
            <v-flex xs12 sm12 md4>
                <v-card
                    class="mx-auto my-12"
                    max-width="374">
                    <template slot="progress">
                    <v-progress-linear
                        color="deep-purple"
                        height="10"
                        indeterminate
                    ></v-progress-linear>
                    </template>

                    <v-img
                    height="250"
                    src="../assets/icons/interaction.jpg"
                    ></v-img>

                    <v-card-title>Interactif</v-card-title>

                    <v-card-text>
                  
                    <div>Partagez vos connaissances auprès de la communauté.</div>
                    </v-card-text>
                </v-card>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    name: 'HomeFeatures'
};
</script>

<style scoped>
</style>