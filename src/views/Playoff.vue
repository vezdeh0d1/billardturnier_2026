<template>
  <section id="playoff" class="section playoff-section">
    <div class="playoff-container">
      <div class="playoff-header">
        <h2 class="section-title">Playoff</h2>
      </div>

      <div class="bracket-wrapper">
        <div class="bracket-board">
          <div class="node" style="left: 0px; top: 20px">
            <MatchCard
              round="Upper Bracket"
              team1="TBD"
              team2="TBD"
              team1Href="#team-1"
              team2Href="#team-2"
              :score1="0"
              :score2="0"
            />
          </div>

          <div class="node" style="left: 0px; top: 220px">
            <MatchCard
              round="TBD"
              team1="TBD"
              team2="TBD"
              team1Href="#team-3"
              team2Href="#team-4"
              :score1="0"
              :score2="0"
            />
          </div>

          <div class="node" style="left: 360px; top: 120px">
            <MatchCard
              round="Upper Bracket"
              team1="TBD"
              team2="TBD"
              team1Href="#teams"
              team2Href="#teams"
              :score1="0"
              :score2="0"
            />
          </div>

          <div class="node" style="left: 0px; top: 470px">
            <MatchCard
              round="Lower Bracket"
              team1="TBD"
              team2="TBD"
              team1Href="#team-5"
              team2Href="#team-6"
              :score1="0"
              :score2="0"
            />
          </div>

          <div class="node" style="left: 0px; top: 670px">
            <MatchCard
              round="Lower Bracket"
              team1="TBD"
              team2="TBD"
              team1Href="#team-7"
              team2Href="#team-8"
              :score1="0"
              :score2="0"
            />
          </div>

          <div class="node" style="left: 360px; top: 500px">
            <MatchCard
              round="Lower Bracket"
              team1="TBD"
              team2="TBD"
              team1Href="#teams"
              team2Href="#teams"
              :score1="0"
              :score2="0"
            />
          </div>

          <div class="node" style="left: 360px; top: 700px">
            <MatchCard
              round="Lower Bracket"
              team1="TBD"
              team2="TBD"
              team1Href="#teams"
              team2Href="#teams"
              :score1="0"
              :score2="0"
            />
          </div>

          <div class="node" style="left: 720px; top: 600px">
            <MatchCard
              round="Lower Bracket"
              team1="TBD"
              team2="TBD"
              team1Href="#teams"
              team2Href="#teams"
              :score1="0"
              :score2="0"
            />
          </div>

          <div class="node" style="left: 1120px; top: 345px">
            <MatchCard
              round="Grand Final"
              team1="TBD"
              team2="TBD"
              team1Href="#teams"
              team2Href="#teams"
              :score1="0"
              :score2="0"
              :isFinal="true"
            />
          </div>

          <!-- CONNECTORS -->
          <div
            class="line h"
            style="left: 260px; top: 123px; width: 80px"
          ></div>
          <div
            class="line h"
            style="left: 260px; top: 323px; width: 80px"
          ></div>
          <div
            class="line v"
            style="left: 338px; top: 123px; height: 200px"
          ></div>
          <div
            class="line h"
            style="left: 338px; top: 223px; width: 22px"
          ></div>

          <div
            class="line h"
            style="left: 260px; top: 573px; width: 100px"
          ></div>
          <div
            class="line h"
            style="left: 260px; top: 773px; width: 100px"
          ></div>

          <div
            class="line h"
            style="left: 620px; top: 603px; width: 60px"
          ></div>
          <div
            class="line h"
            style="left: 620px; top: 803px; width: 60px"
          ></div>
          <div
            class="line v"
            style="left: 678px; top: 603px; height: 200px"
          ></div>
          <div
            class="line h"
            style="left: 678px; top: 703px; width: 42px"
          ></div>

          <div
            class="line h"
            style="left: 620px; top: 223px; width: 398px"
          ></div>
          <div
            class="line h"
            style="left: 980px; top: 703px; width: 40px"
          ></div>
          <div
            class="line v"
            style="left: 1018px; top: 223px; height: 480px"
          ></div>
          <div
            class="line h"
            style="left: 1018px; top: 445px; width: 102px"
          ></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import MatchCard from "../components/MatchCard.vue";

export default {
  name: "Playoff",
  components: {
    MatchCard,
  },
};
</script>

<style scoped>
.playoff-container {
  width: 100%;
  max-width: 1500px;
  margin: 0 auto;
  padding: 0 24px;
}

.playoff-header {
  margin-bottom: 24px;
}

.bracket-wrapper {
  overflow-x: auto;
  padding-bottom: 12px;
}

.bracket-board {
  position: relative;
  min-width: 1400px;
  height: 980px;
}

.node {
  position: absolute;
}

.line {
  position: absolute;
  background: rgba(255, 255, 255, 0.24);
}

.line.h {
  height: 2px;
}

.line.v {
  width: 2px;
}

@media (max-width: 900px) {
  .playoff-container {
    padding: 0 16px;
  }

  .bracket-board {
    min-width: 1400px;
  }
}
</style>
