<template>
  <section id="teams" class="section">
    <div class="container">
      <div class="teams-header">
        <h2 class="section-title">Teams</h2>
      </div>

      <div class="teams-grid">
        <article
          v-for="team in teams"
          :key="team.id"
          :id="team.anchor"
          class="team-card"
        >
          <div class="team-card-top">
            <h3 class="team-name">{{ team.name }}</h3>
          </div>

          <div class="team-members">
            <h4 class="team-subtitle">Mitglieder</h4>
            <ul class="members-list">
              <li v-for="member in team.members" :key="member">
                {{ member }}
              </li>
            </ul>
          </div>

          <div class="team-description" v-if="team.description">
            <h4 class="team-subtitle">Kurzbeschreibung</h4>
            <p>{{ team.description }}</p>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script>
import { teams } from "../data/teams";

export default {
  name: "Teams",
  data() {
    return {
      teams,
    };
  },
};
</script>

<style scoped>
.teams-header {
  margin-bottom: 24px;
}

.teams-text {
  margin-top: 16px;
  max-width: 800px;
}

.teams-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 24px;
}

.team-card {
  scroll-margin-top: 100px;
  background: linear-gradient(
    180deg,
    rgba(255, 255, 255, 0.05),
    rgba(255, 255, 255, 0.025)
  );
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 22px;
  padding: 28px;
  color: #fff;
  box-shadow: 0 14px 40px rgba(0, 0, 0, 0.22);
  transition:
    transform 0.2s ease,
    border-color 0.2s ease,
    box-shadow 0.2s ease;
}

.team-card:hover {
  transform: translateY(-3px);
  border-color: rgba(154, 151, 232, 0.45);
  box-shadow: 0 18px 45px rgba(0, 0, 0, 0.28);
}

.team-card-top {
  margin-bottom: 18px;
}

.team-badge {
  display: inline-block;
  margin-bottom: 10px;
  padding: 6px 10px;
  border-radius: 999px;
  background: rgba(154, 151, 232, 0.16);
  color: #c7c4ff;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.03em;
  text-transform: uppercase;
}

.team-name {
  font-size: 24px;
  font-weight: 600;
  line-height: 1.2;
}

.team-members,
.team-description {
  margin-top: 18px;
}

.team-subtitle {
  margin-bottom: 10px;
  font-size: 14px;
  font-weight: 600;
  color: rgba(255, 255, 255, 0.75);
  text-transform: uppercase;
  letter-spacing: 0.04em;
}

.members-list {
  padding-left: 18px;
  color: rgba(255, 255, 255, 0.9);
}

.members-list li + li {
  margin-top: 6px;
}

.team-description p {
  line-height: 1.7;
  color: rgba(255, 255, 255, 0.88);
}

@media (max-width: 900px) {
  .teams-grid {
    grid-template-columns: 1fr;
  }
}
</style>
