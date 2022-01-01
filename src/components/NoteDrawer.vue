   
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
            label="Name"
            outlined
            v-model="name"
          ></v-text-field>
          </v-list-item>
        <v-list-item>
         <v-textarea
            label="Note"
            outlined
            v-model="note"
          ></v-textarea>
          </v-list-item>
        <v-list-item>
          </v-list-item>

        <v-list-item>
            <v-btn block @click="SaveNoteInfo">Save</v-btn>
          </v-list-item>

      </v-list>
    </v-navigation-drawer>
</template>



<script>
export default {
name: "NoteDrawer",
props : ["drawer",],
model: {
  prop:'drawer',
  event: 'drawerChange'
},
data: function()
{
  return{
    group:null,
    name: "",
    note: ""
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
    SaveNoteInfo: function()
    {
        this.$emit('savenoteinfo',
        {
            Name: this.name,
            Note : this.note,
            CurrentDate: new Date().toLocaleString().replace(',','')
        });
        this.curDrawer = false;

    }

}
}
</script>

<style>
</style>
