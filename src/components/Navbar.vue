<template>
    <nav>
        <v-toolbar class="purple">
             <v-app-bar-nav-icon app class="white--text" @click="drawer=!drawer"></v-app-bar-nav-icon>
             <v-spacer></v-spacer>
             <v-toolbar-title class="text-uppercase white--text">
                <h4>ghss, mtp</h4>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <Popup/>
            <v-btn small depressed fab class="light purple">
                <v-icon fab class="white--text">mdi-share</v-icon>
            </v-btn>
            <v-btn depressed fab class="light purple">
                <v-icon class="white--text">mdi-dots-vertical</v-icon>
            </v-btn>
        </v-toolbar>

        <v-navigation-drawer v-model="drawer" app temporary class="light purple">
           <v-list class="my-10">
               <v-list-item v-for="link in links" :key="link.title" router :to="link.route">
                   <v-list-item-action>
                       <v-icon class="white--text">{{ link.icon }}</v-icon>
                   </v-list-item-action>
                   <v-list-item-content>
                       <v-list-item-title class="white--text">{{ link.title }}</v-list-item-title>
                   </v-list-item-content>
               </v-list-item>
           </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
import Popup from './Popup.vue';

export default {
    components : { Popup },
    data() {
        return {
            drawer: false,
            links: [
                {icon:'mdi-home', title:'Home', route:'/'},
                {icon:'mdi-school', title:'Toppers', route:'/toppers'},
                {icon:'mdi-account-multiple', title:'Management', route:'/management'}
            ]
        }
    }
}
</script>
