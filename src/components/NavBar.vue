<template>
<nav>
    <v-toolbar flat app>
        <v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title class="text-uppercase grey--text"><span class="font-weight-light">TechNo</span><span>Application</span></v-toolbar-title>
    </v-toolbar>
    <v-navigation-drawer v-model="drawer" app class="bg-deep-purple">
        <v-list :height="100">
            <v-list-item :density="compact" prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg" title="Pralay Mondal" subtitle="connect.me@gmail.com"></v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list-item density="compact">
            <v-list-item
                v-for="(item, i) in links"
                :key="i"
                :value="item"
                link :to="item.path"
                color="primary"
            >
                <template v-slot:prepend>
                <v-icon :icon="item.icon"></v-icon>
                </template>

                <v-list-item-title v-text="item.text"></v-list-item-title>
            </v-list-item>
        </v-list-item>
    </v-navigation-drawer>
</nav>
</template>

<script>
export default {
    name: 'NavBar',
    data: () => ({
        drawer: false,
        links:[
            {icon:'mdi-view-dashboard' , text:'Dashboard', path:'/' },
            {icon:'mdi mdi-silverware' , text:'Menus', path:'/menu' },
            {icon:'mdi mdi-currency-inr', text:'Price List', path:'/price' },
            {icon:'mdi-account-box', text:'Contact Us', path:'/contact' },
        ],
    }),
}
</script>
