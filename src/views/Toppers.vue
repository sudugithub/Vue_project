<template>
   <v-container>
      <h1 class="d-block text-center my-6 pa-4">Toppers from 12th Standard</h1>
      <v-toolbar xs12 md12 dense class="mb-3">
        <v-text-field hide-details placeholder="search here" v-model="search" prepend-icon="mdi-magnify"></v-text-field>
      </v-toolbar>
      <v-card class="pa-5" flat v-for="student in filteredStudents" :key="student.name">
        <v-layout row wrap>
          <v-flex xs12 md4>
            <div class="grey--text">Name</div>
            <div>{{ student.name }}</div>
          </v-flex>
          <v-flex xs3 md2>
            <div class="grey--text">Rank</div>
            <div>{{ student.rank }}</div>
          </v-flex>
          <v-flex xs3 md2>
            <div class="grey--text">Marks</div>
            <div>{{ student.marks }}</div>
          </v-flex>
          <v-flex xs3 md2>
            <div class="grey--text">Section</div>
            <div>{{ student.section }}</div>
          </v-flex>
          <v-flex xs3 md2>
            <div class="grey--text">Department</div>
            <div>{{ student.department }}</div>
          </v-flex>
        </v-layout>
      </v-card>
  </v-container>
</template>

<script>

export default {
  data() {
    return {
       students: [
        {rank:1, name:'Sekar', marks:569, section:'A', department: 'Biology'},
        {rank:2, name:'Rasiga', marks:550, section: 'B', department: 'Computerscience'},
        {rank:3, name:'Selvi', marks:529, section:'A', department: 'Biology'},
        {rank:4, name:'Raja', marks:515, section:'C', department: 'History'},
        {rank:5, name:'Mani', marks:512, section:'B', department: 'Computerscience'},
        {rank:6, name:'Aakash', marks:492, section:'C',  department: 'History'},
        {rank:7, name:'Bala', marks:489, section: 'A', department: 'Biology'},
        {rank:8, name:'Chitra', marks:489, section:'B', department: 'Computerscience'},
        {rank:9, name:'Sundaram', marks:485, section:'A',department: 'Biology'},
        {rank:10, name:'Prema', marks:482, section:'C',  department: 'History'}
      ],
      search:''
    }
  },
  computed: {
    filteredStudents: function() {
      return this.students.filter((student)=>{
        return student.name.match(this.search)
      });
    }
  }
}
</script>