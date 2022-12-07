<template>

    <nav class="navbar is-info" role="navigation" aria-label="main navigation">
        <div class="container">
            <div class="navbar-brand">
                <router-link class="navbar-item has-text-weight-semibold" :to="{ name: 'countries' }">
                    WikiCountries
                </router-link>
            </div>
        </div>
    </nav>

</template>

<style scoped>
.navbar {
    margin-bottom: 50px;
    padding: 20px 10px;
}
</style>