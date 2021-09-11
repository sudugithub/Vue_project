<template>
    <v-container class="my-5">
      <h1 class="heading text-center">Management</h1>
      <v-layout column wrap class="text-center">
        <v-flex xs12 sm12 md12 v-for="person in team" :key="person.name">
          <v-card class="ma-3">
            <v-responsive>
              <v-avatar size="150">
                <img :src="person.avatar">
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="subheading">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>

    </v-container>
</template>

<script>

export default {
    data() {
        return {
            team: [
        { name: 'Raja Mani', role: 'Chairman', avatar: '/img_1.png' },
        { name: 'Geethambiga', role: 'Head Miss', avatar: '/img_2.jpg' },
        { name: 'Anusuya', role: 'Assistant HM(11-12)', avatar: '/img_3.jpg' },
        { name: 'Maalathi', role: 'Assistant HM(9-10)', avatar: '/img_4.png' },
        { name: 'Anuratha', role: 'Assistant HM(6-8)', avatar: '/img_5.jpg'}
      ]
        }
    }
}
</script>