<template>
  <article class="match-card" :class="{ 'match-card--final': isFinal }">
    <div class="match-card__header">
      <p class="match-card__round">{{ round }}</p>
    </div>

    <div class="match-card__body">
      <div
        class="match-card__team"
        :class="{ 'match-card__team--winner': score1 > score2 }"
      >
        <a
          :href="team1Href"
          class="match-card__team-name"
          @click.prevent="scrollToTeam(team1Href)"
        >
          {{ team1 }}
        </a>
        <span class="match-card__score">{{ score1 }}</span>
      </div>

      <div
        class="match-card__team"
        :class="{ 'match-card__team--winner': score2 > score1 }"
      >
        <a
          :href="team2Href"
          class="match-card__team-name"
          @click.prevent="scrollToTeam(team2Href)"
        >
          {{ team2 }}
        </a>
        <span class="match-card__score">{{ score2 }}</span>
      </div>
    </div>
  </article>
</template>

<script>
export default {
  name: "MatchCard",
  props: {
    round: {
      type: String,
      default: "Upper Bracket",
    },
    team1: {
      type: String,
      default: "Team 1",
    },
    team2: {
      type: String,
      default: "Team 2",
    },
    team1Href: {
      type: String,
      default: "#teams",
    },
    team2Href: {
      type: String,
      default: "#teams",
    },
    score1: {
      type: Number,
      default: 0,
    },
    score2: {
      type: Number,
      default: 0,
    },
    isFinal: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    scrollToTeam(href) {
      const id = href.replace("#", "");
      const el = document.getElementById(id);

      if (el) {
        el.scrollIntoView({
          behavior: "smooth",
          block: "start",
        });
      }
    },
  },
};
</script>

<style scoped>
.match-card {
  width: 260px;
  border-radius: 18px;
  background: linear-gradient(
    180deg,
    rgba(255, 255, 255, 0.05),
    rgba(255, 255, 255, 0.025)
  );
  border: 1px solid rgba(255, 255, 255, 0.08);
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.24);
  overflow: hidden;
}

.match-card--final {
  border-color: rgba(154, 151, 232, 0.45);
  box-shadow: 0 14px 38px rgba(154, 151, 232, 0.18);
}

.match-card__header {
  padding: 12px 14px 10px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
}

.match-card__round {
  margin: 0;
  font-size: 11px;
  font-weight: 700;
  line-height: 1.4;
  color: rgba(255, 255, 255, 0.72);
  text-transform: uppercase;
  letter-spacing: 0.04em;
}

.match-card__body {
  display: flex;
  flex-direction: column;
}

.match-card__team {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  padding: 14px;
  background: rgba(22, 22, 22, 0.92);
}

.match-card__team + .match-card__team {
  border-top: 1px solid rgba(255, 255, 255, 0.06);
}

.match-card__team-name {
  font-size: 17px;
  font-weight: 500;
  color: var(--color-accent);
  border-bottom: 1px solid transparent;
  transition:
    color 0.2s ease,
    border-color 0.2s ease;
}

.match-card__team-name:hover {
  color: var(--color-accent-light);
  border-color: var(--color-accent-light);
}

.match-card__score {
  min-width: 34px;
  height: 34px;
  padding: 0 10px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.08);
  font-size: 15px;
  font-weight: 700;
  color: #fff;
}

.match-card__team--winner .match-card__team-name {
  font-weight: 700;
}

.match-card__team--winner .match-card__score {
  background: rgba(154, 151, 232, 0.22);
  color: #d8d5ff;
}
</style>
