<template>
  <v-container>
    <div class="pa-3 display-1">Talent Details</div>
    <br/>

        <v-card-media
          src="https://cdn-images-1.medium.com/max/1600/1*8r6hvv5E-FOOdKOih4G7Hg.jpeg"
          height="200px"
        ></v-card-media>

        <v-card-title primary-title>
          <div>
            <i><small>Applicant ID: 201807283716</small></i>
            <h3 class="headline mb-0"><b>Portfolio Projects</b></h3>
            <div>
                <ul style="list-style-type:square">
                <li> <a href="">Blocks</a> : An intuitive reporting platform used by political campaigns and issue advocacy organizations. Blocks organizes all of the program's data in one place; Data is synchronized dynamically so that people can spend less time connecting to data and more time producing critical insights about the program.</li>
                <br/>
                <li> <a href="">Downbeat</a> : A platform for artists to share their music with their fans. The web application allows artists to grow their audience through social media engagement. Users follow the artist on Twitter, SoundCloud, or Youtube, and in exchange they receive access to song downloads.</li>
                <br/>
                <li> <a href="">Polling Location Lookup Tool</a> : A responsively designed web app allowing voters to find the closest polling location to their current location or address. This tool uses geolocation and GIS to empower voters to locate the easiest site for them to use to cast their vote. This product was developed with Nevada in mind, and accommodates Nevada's unique early voting system. Even though early voting locations vary by day, the Polling Location Lookup always allows voters to find the closest open polling location to them each day. The functions of this tool are modular, and can operate as a stand alone site or they can be embedded in existing sites or resources. This tool was used in Nevada by President Barack Obama's Re-Election Campaign in 2012.</li>
                <br/>
                </ul>
            </div>

            <h3 class="headline mb-0"><b>Competitions</b></h3>
            <div>
                <div> <b>Individual</b></div>
                <ul style="list-style-type:square">
                <li> Hacker Rank : <a href="https://www.hackerrank.com/contests/openbracket-2017">OpenBracket Delaware</a> Top 120 (2811 contestants) </li>
                <li> Hacker Rank : <a href="">CodeAgon</a> Top100 (1837 contestants) </li>
                </ul>

                <div> <b>Team</b></div>
                <ul style="list-style-type:square">
                <li> Kaggle : <a href="https://www.kaggle.com/c/avito-demand-prediction/leaderboard">Avito Demand Prediction Challenge </a> Top25 (1917 teams) </li>
                <li> Kaggle : <a href="https://www.kaggle.com/c/talkingdata-adtracking-fraud-detection"> TalkingData AdTracking Fraud Detection Challenge </a> Top180 (3967 teams) </li>
                </ul>
                <br/>
            </div>

            <h3 class="headline mb-0"><b>Voluntary Works</b></h3>
            <div>
                <ul style="list-style-type:square">
                <li> <a href="https://www.womenwhocode.com/singapore">Women Who Code Singapore</a> : Event & Meet-Ups coordinator</li>
                <li> <a href="https://www.datakind.org/chapters/datakind-sg">DataKind SG</a> : Data Cleaning & Exploratory Analysis</li>
                <br/>
                </ul>
            </div>

        </div>

        </v-card-title>

        <v-card-actions>
          <v-spacer/>
          <v-btn>Send Invitation Email</v-btn>
        </v-card-actions>
  </v-container>
</template>
<script>
  export default {
    data () {
      return {
      }
    }
  }
</script>
