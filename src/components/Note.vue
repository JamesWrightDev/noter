<template>
  </v-flex>
      <v-flex md3>
        <v-list subheader>
          <v-subheader>Todo:</v-subheader>
          <v-list-tile
            v-for="item in notes"
            :key="item.title"
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

</template>
<script>
export default {
    data(){
        return{
            notes:[{title: 'hello'}],
        }
    },
}
</script>
