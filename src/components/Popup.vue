<template>
    <v-dialog max-width="600px" v-model="dialog">
        <template v-slot:activator="{on}">
            <v-btn depressed small class="light purple white--text" v-on="on">
                <span>Register</span>
                <v-icon class="light purle white--text ml-1" small left>mdi-pencil</v-icon>
            </v-btn>
        </template>
        <v-card>
            <v-card-title class="purple white--text">
                <h2>Register for admission</h2>
            </v-card-title>
            <v-card-text>
                <v-form class="mx-5" ref="form">
                    <v-text-field label="Name" v-model="name" prepend-icon="mdi-account-circle" :rules="validateName"></v-text-field>
                    <v-menu offset-y min-width="auto">
                         <template v-slot:activator="{ on }">
                             <v-text-field label="Date of Birth" :value="dob" :rules="validateDate" v-on="on" prepend-icon="mdi-calendar"></v-text-field>
                         </template>
                        <v-date-picker v-model="dob"></v-date-picker>               
                    </v-menu>
                    <v-text-field label="Phone number" v-model="phoneNo" :rules="validatePhNo" prepend-icon="mdi-phone"></v-text-field>
                    <v-btn class="purple white--text" @click="submit()">submit</v-btn>
                </v-form>
            </v-card-text>
        </v-card>
        
    </v-dialog> 
</template>

<script>

export default {
    data() {
        return {
            name: '',
            dob: null,
            phoneNo: '',
            validateName: [
                v => /[a-z]+$/.test(v) || 'Enter valid Name'
            ],
            validatePhNo: [
                v => /\d+$/.test(v) || 'Enter numbers only'
            ],
            validateDate: [
                v => /\d/.test(v) || 'Enter valid date'
            ],
            dialog : false
        }
    },
    methods: {
        submit() {
            if(this.$refs.form.validate()){
                 console.log(this.name,this.dob,this.phoneNo);
                 this.dialog = false;
            }
        }
        
    }
}
</script>
