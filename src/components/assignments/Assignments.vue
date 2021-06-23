<!-- not able to use table in < v1.5 -->
<template>
  <v-layout row>
    <v-flex xs12 m6>
      <v-card>
        <v-toolbar color="cyan" dark>

          <v-toolbar-title>Assignments issued</v-toolbar-title>
          <v-spacer></v-spacer>

          <v-btn icon>
            <v-icon>search</v-icon>
          </v-btn>
        </v-toolbar>
        <v-list subheader>
          <v-subheader>Last updated {{ new Date() | formatDateTime}}</v-subheader>
          <template v-for="(item, index) in assignmentData">
            <v-list-tile
            :key="item.title"
            avatar
            ripple
            @click="() => {}"
          >
            <v-list-tile-avatar>
              <v-progress-circular :value="item.completion" :color="item.completion === 100 ? 'green' : item.completion >= 50 ? 'teal' : ''"><small>{{item.completion}}</small></v-progress-circular>
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>{{item.title}} - 
                <template v-for="i in 5">
                  <v-icon v-if="i <= item.difficulty" :key="'star--' + i" color="yellow darken-2">star</v-icon>
                  <v-icon v-else :key="'star--' + i" color="grey lighten-1">star_border</v-icon>
                </template>
              </v-list-tile-title>
            </v-list-tile-content>
            <v-list-tile-action>
              <v-list-tile-action-text>{{ item.testTaken | formatDateTime}}</v-list-tile-action-text>
              <v-icon :color="item.isActive ? 'teal' : 'grey'">assignment_turned_in</v-icon>
            </v-list-tile-action>
          </v-list-tile>
          <v-divider
            v-if="index + 1 < assignmentData.length"
            :key="index"
          ></v-divider>
          </template>
        </v-list>
      </v-card>
    </v-flex>
  </v-layout>
  <!-- <v-card class="d-flex pa-2">
    <v-data-table
      :headers="headers"
      :items="data"
      :items-per-page="30"
      class="elevation-1"
  >
    <template slot-scope="props">
      {{props}}
      <td class="text-xs-right">{{ props.item.testTaken }}</td>
      <td class="text-xs-right">{{ props.item.title }}</td>
      <td class="text-xs-right">{{ props.item.difficulty }}</td>
      <td class="text-xs-right">{{ props.item.completion }}</td>
      <td class="text-xs-right">{{ props.item.isActive }}</td>
    </template>
  </v-data-table>
  </v-card> -->
</template>

<script>
import moment from 'moment'
import assignmentData from "./assignementDate";
export default {
  name: "Assignments",
  data() {
    return {
      headers: [
        {
          text: "Test Taken",
          align: "start",
          sortable: true,
          value: "testTaken"
        },
        { text: "Taker", value: "title" },
        { text: "Level", value: "difficulty" },
        { text: "Completion (%)", value: "completion" },
        { text: "Active", value: "isActive" }
      ],
      assignmentData,
    }
  },
  filters: {
    formatDateTime (val) {
      if (val) {
        console.log(moment(String(val)))
        return moment(String(val)).format('MM/DD/YYYY hh:mm')
    }
    }
  }
};
</script>
