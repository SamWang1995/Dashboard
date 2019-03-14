<template>
    <nav>
        <v-snackbar v-model="snackbar" :timeout="4000" top color="success">
            <span>Awesome! You added a new project.</span>
            <v-btn flat color="white" @click="snackbar = false">Close</v-btn>
        </v-snackbar>
        <v-toolbar flat app>
            <v-toolbar-side-icon class="grey--text" @click="drawer = !drawer"></v-toolbar-side-icon> 
            <v-toolbar-title class="text-uppercase grey--text">
                <span class="font-weight-light">Hello</span>
                <span>Sam</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn flat color="grey">
                <span>Sign Out</span>
                <v-icon right>exit_to_app</v-icon>
            </v-btn>
        </v-toolbar>
        <v-navigation-drawer app v-model="drawer" class="primary">  
            <v-layout column align-center>
                <v-flex class="mt-5 mb-4">
                    <Popup />
                </v-flex>
            </v-layout>
            <v-list>
                <v-list-tile v-for="link in links" :key="link.text" router :to="link.route">
                    <v-list-tile-action>
                        <v-icon class="white--text">{{ link.icon }}</v-icon>
                    </v-list-tile-action>
                    <v-list-tile-content>
                        <v-list-tile-title class="white--text">{{link.text}}</v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
            </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
import Popup from "./Popup";
export default {
    components: { Popup },
    data(){
        return{
            drawer: false,
            links: [
                { icon: 'dashboard', text: 'Dashboard', route: '/' },
                { icon: 'folder', text: 'My Projects', route: '/projects' },
                { icon: 'person', text: 'About', route: '/about' },
                { icon: 'folder', text: 'Chart Project', route: '/chartproject'}
            ],
            snackbar: false
        }
    }
}
</script>
