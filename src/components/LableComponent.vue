<template>
  <v-flex style="" >
    <v-row style="font-size: small">
    {{LabelName}}
    </v-row>

    <v-row style="color:black" >
    {{DataValue}}
    </v-row>
    <v-row style="padding-top:5%"> <v-spacer></v-spacer>  </v-row>
  </v-flex>

</template>

<script>
export default {
name: "LableComponenet",
props: ["LabelName","DataValue"]
}
</script>

<style>

</style>