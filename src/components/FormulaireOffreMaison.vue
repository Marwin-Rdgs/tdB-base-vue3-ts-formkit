<script setup lang="ts">
    import { ref } from "@vue/reactivity";
    import cardoffre from "./card.vue";

    // On fait une variable réactive qui réactive qui réference les données
    // ATTENTION : faire une Ref pas une Reactive car :
    // c'est l'objet qui doit être réactif, pas ses props
    const maison = ref({nom:"test", price:34, favoris:true, txt:"produit de test", nbbath:2, nbsize:"test m²", img:"/public/card.jpg"});
</script>

<template>
    <div>
        <div class="p-2">
            <h2 class="text-2xl">Résultat (Prévisualisation)</h2>
            <!-- Optionnel on affiche les données -->
            <cardoffre v-bind="maison" />
        </div>
        <div class="p-2">
            <!-- On passe la "ref" à Formkit -->
            <Formkit type="form" v-model="maison">
                <Formkit name="nom" label="nom" />
                <Formkit name="price" label="prix" type="number"/>
                <Formkit name="favoris" label="mettre en valeur" type="checkbox"/>
            </Formkit>
        </div>
    </div>
</template>