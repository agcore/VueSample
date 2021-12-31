<template>
  <v-container>
    <v-row class="text-center">
      {{textsample}}

    </v-row>
        <v-row class="text-center">

                <v-text-field
            label="Name"
            outlined
            v-model.lazy="textsample"
          ></v-text-field>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
        textsample:"",
        counter: 1
    }),
  }
</script>
