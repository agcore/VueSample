   
<template>
      <v-navigation-drawer
      v-model="curDrawer"
      absolute
      bottom
      temporary
      right
      width="25%"
    >
          <v-list
        
        dense
      >

          <v-list-item>
         <v-text-field
            label="Email"
            outlined
            v-model="email"
          ></v-text-field>
          </v-list-item>
                    <v-list-item>
         <v-text-field
            label="Address"
            outlined
            v-model="address"
          ></v-text-field>
          </v-list-item>
        <v-list-item>
         <v-text-field
            label="Language"
            outlined
            v-model="language"
          ></v-text-field>
          </v-list-item>

        <v-list-item>
            <v-btn block @click="SaveContactInfo">Save</v-btn>
          </v-list-item>

      </v-list>
    </v-navigation-drawer>
</template>



<script>
export default {
name: "CustomDrawer",
props : ["drawer","contactInfo"],
model: {
  prop:'drawer',
  event: 'drawerChange'
},
data: function()
{
  return{
    editedSaying:"",
    group:null,
    email: this.contactInfo.Email,
    address: this.contactInfo.Address,
    language: this.contactInfo.Language,
  }
},
computed : {
  curDrawer : {
    get: function()
    {
      return this.drawer
    },
    set : function(value)
    {
      this.$emit('drawerChange',value);
    }
  },
},
methods:{
    SaveContactInfo: function()
    {
        this.$emit('savecontactinfo',
        {
            Email: this.email,
            Address : this.address,
            Language: this.language
        });
        this.curDrawer = false;

    }

}
}
</script>

<style>
</style>
