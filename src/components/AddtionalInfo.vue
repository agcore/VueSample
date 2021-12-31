<template>
  
    <v-card
    outlined
    min-width="49.5%">
    <v-card-subtitle>
        <h2>Additional Information</h2>
    </v-card-subtitle>
    <v-card-text>

      <v-row

        no-gutters
      >
        <v-col  cols="12" style="padding:5%">
            
            <LableComponent :LabelName="'Date of birth'" :DataValue="'04 September, 1993'"/>
            <LableComponent :LabelName="'Pronouns'" :DataValue="'N/A'"/>
            <LableComponent :LabelName="'Prefered contact channel'" :DataValue="'Mobile phone'"/>
            <LableComponent :LabelName="'Loyalty Points'" :DataValue="'15000'"/>
        </v-col>
        
        
      </v-row>


    </v-card-text>
    </v-card>



</template>

<script>
import LableComponent from "./LableComponent.vue"
export default {
    name: "AddtionalInfo",
    components:
    {
        LableComponent
    }

}
</script>

<style>

</style>