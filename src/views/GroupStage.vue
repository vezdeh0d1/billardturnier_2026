<template>
  <section id="group-stage" class="section">
    <div class="container">
      <div class="group-stage-header">
        <h2 class="section-title">Group Stage</h2>
        <p class="section-text group-stage-text">
          In der Ligaphase tritt jedes Team gegen jedes andere Team in einem
          Best-of-2 an. Die Ergebnisse werden in die Tabelle eingetragen. Klickt
          auf einen Teamnamen, um direkt zum jeweiligen Team im unteren Bereich
          zu springen.
        </p>
      </div>

      <div class="table-wrapper">
        <table class="group-table">
          <thead>
            <tr>
              <th class="corner-cell">Teams</th>
              <th v-for="team in teams" :key="team.id">
                <a
                  class="team-link"
                  :href="`#${team.anchor}`"
                  @click.prevent="scrollToTeam(team.anchor)"
                >
                  {{ team.name }}
                </a>
              </th>
            </tr>
          </thead>

          <tbody>
            <tr v-for="(rowTeam, rowIndex) in teams" :key="rowTeam.id">
              <th class="row-header">
                <a
                  class="team-link"
                  :href="`#${rowTeam.anchor}`"
                  @click.prevent="scrollToTeam(rowTeam.anchor)"
                >
                  {{ rowTeam.name }}
                </a>
              </th>

              <td
                v-for="(colTeam, colIndex) in teams"
                :key="`${rowTeam.id}-${colTeam.id}`"
                :class="{ diagonal: rowIndex === colIndex }"
              >
                <span v-if="rowIndex === colIndex">—</span>
                <span v-else>{{ matches[rowIndex][colIndex] }}</span>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </section>
</template>

<script>
import { teams } from "../data/teams";
import { matches } from "../data/groupStage";

export default {
  name: "GroupStage",
  data() {
    return {
      teams,
      matches,
    };
  },
  methods: {
    scrollToTeam(anchor) {
      const el = document.getElementById(anchor);
      if (el) {
        el.scrollIntoView({ behavior: "smooth", block: "start" });
      }
    },
  },
};
</script>

<style scoped>
.group-stage-header {
  margin-bottom: 24px;
}

.group-stage-text {
  margin-top: 16px;
  max-width: 900px;
}

.table-wrapper {
  overflow-x: auto;
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  background: rgba(255, 255, 255, 0.03);
}

.group-table {
  width: 100%;
  min-width: 900px;
  border-collapse: collapse;
  color: #fff;
}

.group-table th,
.group-table td {
  padding: 14px 16px;
  text-align: center;
  border: 1px solid rgba(255, 255, 255, 0.08);
  font-size: 14px;
}

.corner-cell {
  min-width: 140px;
  font-weight: 600;
  background: rgba(255, 255, 255, 0.06);
}

.row-header {
  text-align: left;
  min-width: 140px;
  background: rgba(255, 255, 255, 0.04);
}

.team-link {
  color: #fff;
  text-decoration: none;
  font-weight: 500;
  border-bottom: 1px solid transparent;
  transition:
    color 0.2s ease,
    border-color 0.2s ease;
}

.team-link:hover {
  color: #9a97e8;
  border-color: #9a97e8;
}

.group-table thead th {
  background: rgba(255, 255, 255, 0.06);
  font-weight: 600;
}

.group-table td {
  background: rgba(255, 255, 255, 0.02);
}

.group-table td.diagonal {
  background: rgba(255, 255, 255, 0.08);
  color: rgba(255, 255, 255, 0.45);
  font-weight: 600;
}
</style>
