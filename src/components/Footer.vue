<template>
    <v-footer>
        <v-card class="purple white--text text-as-center flex">
            <p class="text-center">
                <v-btn v-for="icon in icons" :key="icon" class="mx-5 mt-2" dark icon>
                   <v-icon size="24px">{{ icon }}</v-icon>
                </v-btn>
            </p>
            <p class="white--text text-center">All copyrights are reserved.&copy;2021</p>
        </v-card>
    </v-footer>
</template>

<script>

export default{
    data() {
        return {
              icons: [
                'mdi-facebook',
                'mdi-twitter',
                'mdi-linkedin',
                'mdi-instagram',
            ]
        }
    }
}
</script>
