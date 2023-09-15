<template>
    <v-app>

        <v-navigation-drawer v-model="drawer" class="bg-deep-purple" theme="dark" expand-on-hover rail>
            <v-list>
                <v-list-item prepend-icon="mdi-account" title="User Name" subtitle="user@asurion.com"></v-list-item>
            </v-list>

            <v-divider></v-divider>

            <v-list density="compact" nav>
                <!-- Vuetify supports Material Design Icons, Material Icons, Font Awesome 4 and Font Awesome 5 -->

                <v-list-item to="/" prepend-icon="mdi-table-large" title="Dashboard" link nuxt></v-list-item>
                <v-list-item to="/demos" prepend-icon="mdi-table-edit" title="Edit" link nuxt></v-list-item>
                <v-list-item to="/security" prepend-icon="mdi-security" title="Security" link></v-list-item>
                <v-list-item to="/contact" prepend-icon="mdi-card-account-mail" title="Contact" link></v-list-item>

                <!-- https://pictogrammers.com/library/mdi/ -->
            </v-list>
        </v-navigation-drawer>

        <v-app-bar density="compact" color="grey-darken-3">


            <v-app-bar-title>Application</v-app-bar-title>

        </v-app-bar>

        <v-main>
            <!-- output the page content -->
            <slot />
        </v-main>
    </v-app>
</template>

<script setup>
import { ref } from 'vue'

const drawer = ref(null)
</script>
  
<script>
export default {
    data: () => ({ drawer: null }),
}
</script>
<style lang="scss">
@use './settings';
</style>

