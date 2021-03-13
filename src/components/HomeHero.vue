<template>
    <v-container fluid fill-height class="home-hero" style="max-height: 100vh;">
        <v-layout justify-center align-center column pa-5>
            <div class="display-4 font-weight-black white--text text-xs-center">DES ALIMENTS SAINS</div>
            <div class="display-4 font-weight-black white--text text-xs-center mb-3">POUR VOTRE CORPS</div>
            <div class="display-4 font-weight-bold white--text text-xs-center">
                 <v-text-field
                    v-model="aliment"
                    :append-icon="'mdi-magnify'"
                    filled
                    clearable
                    rounded
                    label="Saisir un aliment"
                    type="text"
                    @click:append="sendProduct"
                    @keyup.enter.native="sendProduct"
                    @click:clear="hideTable"
                ></v-text-field>
            </div>
            <v-expand-transition>
                <v-data-table v-show="show"
                    :headers="headers"
                    :items="items"
                    :hide-default-footer="true"
                    loading="myloadingvariable"
                    loading-text="Chargement des données"
                    class="elevation-1"
                ></v-data-table>
            </v-expand-transition>
        </v-layout>
    </v-container>
</template>

<script>
import Vue from 'vue';
import axios from 'axios';
import VueAxios from 'vue-axios';
Vue.use(VueAxios, 'vue-axios')

export default {
    name: 'HomeHero',
    data: () => ({
        aliment: '',
        icons: [
            'mdi_magnify',
        ],
        show: false,
        headers: [
            { text: 'Aliment', value: 'product' },
            { text: 'Quantité (g)', value: 'quantity' },
            { text: 'Calories', value: 'calories' },
            { text: 'Protéines (g)', value: 'proteine' },
            { text: 'Sucre (g)', value: 'sugar' },
            { text: 'Glucides (g)', value: 'carbohydrate' },
            { text: 'Cholestérol (g)', value: 'cholesterol' },
            { text: 'Acides gras saturés (g)', value: 'fat_satured' },
            { text: 'Acides gras (g)', value: 'fat' },
            { text: 'Fibre (g)', value: 'fiber' },
            { text: 'Potassium (mg)', value: 'potassium' },
            { text: 'Sodium (mg)', value: 'sodium' },
        ],
        items: [],
        myloadingvariable: false,
    }),


    methods: {
        sendProduct () {
            this.myloadingvariable=true;
            let config = {
                headers: {
                    "X-Api-Key": "MEq6picJZ4OufV1DK7meJQ==LWM5MDlGisNwKV6m"
                }
            }
            console.log(this.aliment)
            this.items = [];
            axios.get("https://api.calorieninjas.com/v1/nutrition?query=" + this.aliment, config)
            .then(rep =>(
                // console.log(rep.data.items[0])
                this.items.push({
                    product: this.aliment,
                    quantity: rep.data.items[0].serving_size_g,
                    calories: rep.data.items[0].calories,
                    proteine: rep.data.items[0].protein_g,
                    sugar: rep.data.items[0].sugar_g,
                    carbohydrate: rep.data.items[0].carbohydrates_total_g,
                    cholesterol: rep.data.items[0].cholesterol_mg,
                    fat_satured: rep.data.items[0].fat_saturated_g,
                    fat: rep.data.items[0].fat_total_g,
                    fiber: rep.data.items[0].fiber_g,
                    potassium: rep.data.items[0].potassium_mg,
                    sodium: rep.data.items[0].sodium_mg,
                })
            ))
            this.show = true;
            this.myloadingvariable=false
        },
        clearMessage () {
            this.aliment = ''
            // this.show = false;
        },
        hideTable(){
            this.show = false;
        }

    },
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
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>