<template>



      <v-container>
        <v-card 
        max-width="60%"
        >          
          <v-card-title>
            <h2>Customer Details</h2> <v-spacer></v-spacer> <v-btn @click.stop="drawer = !drawer">Edit</v-btn>
          </v-card-title>
          
          <v-card-text>
            <v-row style="padding:1%">
            <ContactInformation :contactInfo="contactInformation"/>
            <v-spacer></v-spacer>
            <AddtionalInfo />
            </v-row>
          </v-card-text>  
        </v-card>
        <CustomDrawer v-model="drawer" 
        :contactInfo="contactInformation"
        @savecontactinfo="savecontact"
         />
      </v-container>
    

</template>

<script>
import ContactInformation from './ContactInformation.vue'
import AddtionalInfo from './AddtionalInfo.vue'
import CustomDrawer from './CustomDrawer.vue'

  export default {
    name: 'HelloWorld',
    components: {
      ContactInformation,
      AddtionalInfo,
      CustomDrawer
    },
    methods:
    {
      savecontact: function(data)
      {
        this.contactInformation.Email = data.Email
        this.contactInformation.Address = data.Address
        this.contactInformation.Language = data.Language
      }
    },
    data: () => ({
        textsample:"", 
        counter: 1,
        drawer: false,
        contactInformation : 
        {
          Email: "faisal.test@email.com",
          Address: "1500 Allstate Pkwy, Markham, ON L3R 5B4",
          Language: "English"
        }
    }),
  }
</script>
