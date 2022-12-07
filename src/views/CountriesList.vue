<template>

    <div class="container" style="height: calc(100vh - 52px);">
        <div class="columns mt-0 " style="height: 100%;">
            <div class="column is-4" style="overflow: auto">
                <router-link v-for="countries in countriesList" class="media is-clickable"
                    :to="{ name: 'details', params: { code: countries.alpha3Code } }">
                    <figure class="media-left">
                        <p class="image is-64x64">
                            <img
                                :src="`https://flagpedia.net/data/flags/icon/72x54/${countries.alpha2Code.toLowerCase()}.png`" />
                        </p>
                    </figure>

                    <div class="media-content">
                        <div class="content">
                            <p>
                                <strong>{{ countries.name.common }}</strong>
                            </p>
                        </div>
                    </div>
                </router-link>
            </div>
            <router-view></router-view>
        </div>
    </div>

</template>

<script setup>

import countriesList from '../assets/countries.json';

</script>





