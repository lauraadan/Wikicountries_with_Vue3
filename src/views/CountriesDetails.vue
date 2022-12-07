
<template>

    <div class="column is-8">
        <section class="section">
            <figure class="image is-128x128">
                <img :src="`https://flagpedia.net/data/flags/icon/72x54/${count.alpha2Code.toLowerCase()}.png`">
            </figure>

            <div class="title">{{ count.name.common }}</div>
            <table class="table is-fullwidth">
                <tbody>
                    <tr>
                        <td><strong>Capital</strong></td>
                        <td>{{ count.capital[0] }}</td>
                    </tr>
                    <tr>
                        <td><strong>Area</strong></td>
                        <td>{{ count.area }}km<sup>2</sup></td>
                    </tr>
                    <tr>
                        <td><strong>Borders</strong></td>
                        <td>
                            <ul>
                                <router-link v-for="border in count.borders"
                                    :to="{ name: 'details', params: { code: border } }">
                                    <li> {{ border }}</li>
                                </router-link>
                            </ul>
                        </td>
                    </tr>
                </tbody>
            </table>
        </section>
    </div>
</template>


<script setup>


import { ref, watch } from 'vue'
import countries from '../assets/countries.json';
import { useRoute } from 'vue-router'
const route = useRoute();

function getCountry(code) {
    return countries.find(element => element.alpha3Code == code);
}

const count = ref();

watch(() => {
    count.value = getCountry(route.params.code);
});

</script>

<style scoped>
.section {
    padding: 4rem 2rem;
    border: 1px solid rgb(199, 199, 199);
}
</style>
