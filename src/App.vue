<template>
  <div id="app">
    
    <v-container grid-list-md text-xs-center>
      <v-layout>
      <v-flex xs12 md3>
        <h1>NOTER</h1>
        <v-form v-model="valid">
        <v-text-field
          v-model="newNote"
          :rules="nameRules"
          
          label="Add a new note"
          required
        >
      </v-text-field>
    </v-form>
     </v-flex>
    </v-layout>
    <v-layout row wrap>
      </v-flex>
      <v-flex md3>
        <v-list subheader>
          <v-subheader>Todo:</v-subheader>
          <v-list-tile
            v-for="item in notes"
            :key="item.title"
            avatar
            @click=""
          >
     
            <v-list-tile-content>
              <v-list-tile-title v-html="item.title"></v-list-tile-title>
            </v-list-tile-content>

            <v-list-tile-action>
              <v-icon :color="item.active ? 'teal' : 'grey'">done</v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list>
      </v-flex>
       

    </v-layout>
  </v-container>
  </div>

</template>

<script>
export default {
  name: 'app',
  data () {
    return {
    notes:[{title: 'hello'}],
    newNote:'',  
    }
  },
  methods:{
    addNote: function (event){
      this.notes.push({title:this.newNote, done:false});
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
