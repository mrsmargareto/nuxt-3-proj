<template>
    <v-app id="inspire">
        <v-navigation-drawer theme="dark" v-model="drawer">
            <!--  -->
            <v-list density="compact" nav>
                <!-- Vuetify supports Material Design Icons, Material Icons, Font Awesome 4 and Font Awesome 5 -->
                <v-list-subheader>REPORTS</v-list-subheader>
                <v-list-item v-for="(item, i) in items" :key="i" :value="item" color="primary" rounded="shaped"
                    :to="item.route" link nuxt>

                    <template v-slot:prepend>
                        <v-icon :icon="item.icon"></v-icon>
                    </template>

                    <v-list-item-title v-text="item.text"></v-list-item-title>
                </v-list-item>

                <!-- https://pictogrammers.com/library/mdi/ -->
            </v-list>
        </v-navigation-drawer>

        <v-app-bar theme="dark">
            <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

            <v-app-bar-title>Application</v-app-bar-title>
        </v-app-bar>



        <v-main class="d-flex align-center justify-center" style="min-height: 300px;">
            <!--  -->
            <slot />
        </v-main>
    </v-app>
</template>

<script setup>
import { ref } from 'vue'

const drawer = ref(null)
const items = [
    { text: 'Dashboard', icon: 'mdi-clock', route: '/' },
    { text: 'Edit', icon: 'mdi-account', route: '/edit' },
    { text: 'Security', icon: 'mdi-flag', route: '/security' },
    { text: 'Contact', icon: 'mdi-clock', route: '/contact' },
]
</script>
  
<script>
export default {
    data: () => ({
        items: [
            { text: 'Dashboard', icon: 'mdi-clock', route: '/' },
            { text: 'Edit', icon: 'mdi-account', route: '/edit' },
            { text: 'Security', icon: 'mdi-flag', route: '/security' },
            { text: 'Contact', icon: 'mdi-clock', route: '/contact' },
        ],
    }),
}

</script>