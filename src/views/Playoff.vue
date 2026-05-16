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
              :round="ub1.round"
              :team1="ub1.team1.name"
              :team2="ub1.team2.name"
              :team1Href="`#${ub1.team1.anchor}`"
              :team2Href="`#${ub1.team2.anchor}`"
              :score1="ub1.score1"
              :score2="ub1.score2"
            />
          </div>

          <div class="node" style="left: 0px; top: 220px">
            <MatchCard
              :round="ub2.round"
              :team1="ub2.team1.name"
              :team2="ub2.team2.name"
              :team1Href="`#${ub2.team1.anchor}`"
              :team2Href="`#${ub2.team2.anchor}`"
              :score1="ub2.score1"
              :score2="ub2.score2"
            />
          </div>

          <div class="node" style="left: 360px; top: 120px">
            <MatchCard
              :round="ubf.round"
              :team1="ubf.team1.name"
              :team2="ubf.team2.name"
              :team1Href="`#${ubf.team1.anchor}`"
              :team2Href="`#${ubf.team2.anchor}`"
              :score1="ubf.score1"
              :score2="ubf.score2"
            />
          </div>

          <div class="node" style="left: 0px; top: 470px">
            <MatchCard
              :round="lb1.round"
              :team1="lb1.team1.name"
              :team2="lb1.team2.name"
              :team1Href="`#${lb1.team1.anchor}`"
              :team2Href="`#${lb1.team2.anchor}`"
              :score1="lb1.score1"
              :score2="lb1.score2"
            />
          </div>

          <div class="node" style="left: 0px; top: 670px">
            <MatchCard
              :round="lb2.round"
              :team1="lb2.team1.name"
              :team2="lb2.team2.name"
              :team1Href="`#${lb2.team1.anchor}`"
              :team2Href="`#${lb2.team2.anchor}`"
              :score1="lb2.score1"
              :score2="lb2.score2"
            />
          </div>

          <div class="node" style="left: 360px; top: 500px">
            <MatchCard
              :round="lbs1.round"
              :team1="lbs1.team1.name"
              :team2="lbs1.team2.name"
              :team1Href="`#${lbs1.team1.anchor}`"
              :team2Href="`#${lbs1.team2.anchor}`"
              :score1="lbs1.score1"
              :score2="lbs1.score2"
            />
          </div>

          <div class="node" style="left: 360px; top: 700px">
            <MatchCard
              :round="lbs2.round"
              :team1="lbs2.team1.name"
              :team2="lbs2.team2.name"
              :team1Href="`#${lbs2.team1.anchor}`"
              :team2Href="`#${lbs2.team2.anchor}`"
              :score1="lbs2.score1"
              :score2="lbs2.score2"
            />
          </div>

          <div class="node" style="left: 720px; top: 600px">
            <MatchCard
              :round="lbf.round"
              :team1="lbf.team1.name"
              :team2="lbf.team2.name"
              :team1Href="`#${lbf.team1.anchor}`"
              :team2Href="`#${lbf.team2.anchor}`"
              :score1="lbf.score1"
              :score2="lbf.score2"
            />
          </div>

          <div class="node" style="left: 1120px; top: 345px">
            <MatchCard
              :round="gf.round"
              :team1="gf.team1.name"
              :team2="gf.team2.name"
              :team1Href="`#${gf.team1.anchor}`"
              :team2Href="`#${gf.team2.anchor}`"
              :score1="gf.score1"
              :score2="gf.score2"
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

const APPS_SCRIPT_URL =
  "https://script.google.com/macros/s/AKfycbxYan17E9mWheNcNJWhUfn8mZd2xawJawt4R5wjUVXytGNzSG8vRHSvHLk5oSQpnA/exec";

export default {
  name: "Playoff",
  components: {
    MatchCard,
  },
  data() {
    return {
      teams: [],
      playoffMatches: [],
      loading: true,
      error: "",
    };
  },
  async mounted() {
    try {
      const [teamsRes, matchesRes] = await Promise.all([
        fetch(`${APPS_SCRIPT_URL}?action=teams`),
        fetch(`${APPS_SCRIPT_URL}?action=playoffMatches`),
      ]);

      if (!teamsRes.ok) {
        throw new Error(`Teams request failed: ${teamsRes.status}`);
      }

      if (!matchesRes.ok) {
        throw new Error(`Playoff matches request failed: ${matchesRes.status}`);
      }

      this.teams = await teamsRes.json();
      this.playoffMatches = await matchesRes.json();
    } catch (err) {
      console.error("Playoff loading error:", err);
      this.error = `Could not load playoff data: ${err.message}`;
    } finally {
      this.loading = false;
    }
  },
  methods: {
    getTeamByAnchor(anchor) {
      return this.teams.find((team) => team.anchor === anchor) || null;
    },

    getMatch(matchId) {
      return (
        this.playoffMatches.find((match) => match.matchId === matchId) || null
      );
    },

    getWinner(match) {
      if (!match) return null;
      if (match.score1 === match.score2) return null;

      return match.score1 > match.score2
        ? this.resolveSource(match.team1Source)
        : this.resolveSource(match.team2Source);
    },

    getLoser(match) {
      if (!match) return null;
      if (match.score1 === match.score2) return null;

      return match.score1 > match.score2
        ? this.resolveSource(match.team2Source)
        : this.resolveSource(match.team1Source);
    },

    resolveSource(source) {
      if (!source) return null;

      if (source.startsWith("team:")) {
        const anchor = source.replace("team:", "");
        return this.getTeamByAnchor(anchor);
      }

      if (source.startsWith("winner:")) {
        const matchId = source.replace("winner:", "");
        return this.getWinner(this.getMatch(matchId));
      }

      if (source.startsWith("loser:")) {
        const matchId = source.replace("loser:", "");
        return this.getLoser(this.getMatch(matchId));
      }

      return null;
    },

    getMatchTeams(matchId) {
      const match = this.getMatch(matchId);

      if (!match) {
        return {
          round: "",
          score1: 0,
          score2: 0,
          team1: { name: "TBD", anchor: "teams" },
          team2: { name: "TBD", anchor: "teams" },
        };
      }

      const team1 = this.resolveSource(match.team1Source) || {
        name: "TBD",
        anchor: "teams",
      };

      const team2 = this.resolveSource(match.team2Source) || {
        name: "TBD",
        anchor: "teams",
      };

      return {
        round: match.round,
        score1: match.score1,
        score2: match.score2,
        team1,
        team2,
      };
    },
  },
  computed: {
    ub1() {
      return this.getMatchTeams("ub1");
    },
    ub2() {
      return this.getMatchTeams("ub2");
    },
    ubf() {
      return this.getMatchTeams("ubf");
    },
    lb1() {
      return this.getMatchTeams("lb1");
    },
    lb2() {
      return this.getMatchTeams("lb2");
    },
    lbs1() {
      return this.getMatchTeams("lbs1");
    },
    lbs2() {
      return this.getMatchTeams("lbs2");
    },
    lbf() {
      return this.getMatchTeams("lbf");
    },
    gf() {
      return this.getMatchTeams("gf");
    },
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
