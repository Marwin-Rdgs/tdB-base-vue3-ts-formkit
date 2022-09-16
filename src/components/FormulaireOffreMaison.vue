<script setup lang="ts">
    import { ref } from "@vue/reactivity";
    import cardoffre from "./card.vue";

    // On fait une variable réactive qui réactive qui réference les données
    // ATTENTION : faire une Ref pas une Reactive car :
    // c'est l'objet qui doit être réactif, pas ses props
    const maison = ref({nom:"test-ref-formkit", price:29, favoris:true, txt:"test de formkit", nbbath:4, nbsize:"89 m²", img:"/card.jpg"});
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
            <FormKit type="form" v-model="maison">
                <FormKit name="nom" label="nom" />
                <FormKit name="price" label="prix" type="number"/>
                <FormKit name="favoris" label="mettre en valeur" type="checkbox"/>
            </FormKit>
        </div>
    </div>
</template>