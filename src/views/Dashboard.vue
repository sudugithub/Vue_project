<template>
    <div>
        <v-card xs12 md12 flat class="pa-5"> 
          <h1 class="text-center">Government Higher Secondary School</h1>
          <h3 class="subheading grey--text text-center">Online Portal</h3>
        </v-card>
        <v-container>
          <h1 class="subheading text-center purple white--text">Teaching periods</h1>
          <v-row class="mt-5">
            <v-col xs12 sm3 v-for="url in urlsT" :key="url.imgs">
              <img :src="url.imgs" height="175" width="175">
            </v-col>
          </v-row>
           <h1 class="subheading text-center mt-5 purple white--text">Games periods</h1>
          <v-row class="mt-5">
            <v-col xs12 sm3 v-for="url in urlsG" :key="url.imgs">
              <img :src="url.imgs" height="175" width="175">
            </v-col>
          </v-row>
          <h1 class="subheading text-center mt-5 purple white--text">Yoga periods</h1>
          <v-row class="mt-5">
            <v-col xs12 sm6 v-for="url in urlsY" :key="url.imgs">
              <img :src="url.imgs" height="175" width="175">
            </v-col>
          </v-row>
        </v-container>
    </div>
</template>

<script>

export default {
  data() {
    return {
      urlsT: [
        {imgs:'/Teaching/sclT_1.jpg'},
        {imgs:'/Teaching/sclT_2.jpg'},
        {imgs:'/Teaching/sclT_3.jpg'},
        {imgs:'/Teaching/sclT_4.jpg'}
      ],
      urlsG: [
        {imgs:'/Games/sclG_1.jpg'},
        {imgs:'/Games/sclG_2.jpg'},
        {imgs:'/Games/sclG_3.jpg'},
        {imgs:'/Games/sclG_4.jpg'}
      ],
      urlsY: [
        {imgs:'/Yoga/sclY_1.jpg'},
        {imgs:'/Yoga/sclY_2.jpg'}
      ]
    }
  }
}
</script>
