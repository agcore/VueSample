<template>
  
    <v-card
    outlined
    min-width="50%">
    <v-card-subtitle>
        <h2>Contact information</h2>
    </v-card-subtitle>
    <v-card-text>

      <v-row

        no-gutters
      >
        <v-col  cols="12" style="padding:5%">
            
            <LableComponent :LabelName="'Email'" :DataValue="contactInfo.Email"/>
            <LableComponent :LabelName="'Address'" :DataValue="contactInfo.Address"/>
            <LableComponent :LabelName="'Language'" :DataValue="contactInfo.Language"/>
            <LableComponent :LabelName="'Time Zone'" :DataValue="'Eastern Standard Time'"/>
        </v-col>
        
        
      </v-row>


    </v-card-text>
    </v-card>



</template>

<script>
import LableComponent from "./LableComponent.vue"
export default {
    props: ["contactInfo"],
    name: "ContactInformation",
    components:
    {
        LableComponent
    }

}
</script>

<style>

</style>