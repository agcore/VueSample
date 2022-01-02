<template>



      <v-container>
        <v-row>
        <v-col 
        cols="8"
        >
          <v-card 
          >          
            <v-card-title>
              Customer Details<v-spacer></v-spacer> <v-btn   @click.stop="drawer = !drawer">Edit</v-btn>
            </v-card-title>
            
            <v-card-text>
              <v-row style="padding:1%">
              <ContactInformation :contactInfo="contactInformation"/>
              <v-spacer></v-spacer>
              <AddtionalInfo />
              </v-row>
            </v-card-text>  
          </v-card>
        </v-col>
        <template v-if="features.Notes">
        <v-col
        cols="4">
                            <v-card 
          >          
            <v-card-title>
              Notes ({{notes.length}} notes)
            </v-card-title>
            
            <v-card-text>
               <v-btn block @click.stop="notedrawer = !notedrawer" :disabled="disable.Notes">Add new note</v-btn>
              <v-row v-for="(item,index) in notes" :key="index" style="padding:1%">
                <v-container>
                  <v-card
                  flat
                  outlined>
                  <v-card-title>
                        {{item.Name}}
                    </v-card-title>
                  <v-card-text>
                  <v-row style="padding:1%">
                    <v-col>
                      <v-row>
                      {{item.Date}}
                      </v-row>
                      <v-row>
                      {{item.Note}}
                      </v-row>
                      </v-col>  
                  </v-row>
            </v-card-text>
                  </v-card>
                </v-container>
              </v-row>
            </v-card-text>  
          </v-card>
        </v-col>
        </template>
        </v-row>
        <v-row>
          <v-btn @click="features.Notes = !features.Notes"> Toggle Note Feature</v-btn>
          <v-btn @click="disable.Notes = !disable.Notes"> Toggle Note Feature View Only</v-btn>
        </v-row>
        <NoteDrawer v-model="notedrawer" 
        @savenoteinfo="savenote"
         />
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
import NoteDrawer from './NoteDrawer.vue'

  export default {
    name: 'HelloWorld',
    components: {
      ContactInformation,
      AddtionalInfo,
      CustomDrawer,
      NoteDrawer
    },
    methods:
    {
      savecontact: function(data)
      {
        this.contactInformation.Email = data.Email
        this.contactInformation.Address = data.Address
        this.contactInformation.Language = data.Language
      },
      savenote: function(note)
      {
        this.notes.push({
          Name: note.Name,
          Note:note.Note,
          Date: note.CurrentDate
        })
      }
    },
    data: () => ({
        textsample:"", 
        counter: 1,
        drawer: false,
        notedrawer: false,
        contactInformation : 
        {
          Email: "faisal.test@email.com",
          Address: "1500 Allstate Pkwy, Markham, ON L3R 5B4",
          Language: "English"
        },
        notes: [],
        features: {
          Notes:true,
          ContactInformation:true
        },
        disable:{
          Notes:true
        }
    }),
  }
</script>
