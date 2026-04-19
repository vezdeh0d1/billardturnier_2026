<template>
  <header class="site-header" :class="{ 'scrolled-nav': scrolledNav }">
    <nav class="container nav-inner">
      <div class="branding">
        <h1>BILLIARDTURNIER 2026</h1>
      </div>

      <ul class="navigation">
        <li>
          <a class="link" href="#rules" @click.prevent="scrollToRules">Rules</a>
        </li>
        <li>
          <a
            class="link"
            href="#group-stage"
            @click.prevent="scrollToGroupStage"
          >
            Group Stage
          </a>
        </li>
        <li>
          <a class="link" href="#playoff" @click.prevent="scrollToPlayoff"
            >Playoff</a
          >
        </li>
        <li>
          <a class="link" href="#teams" @click.prevent="scrollToTeams">Teams</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Navigation",
  data() {
    return {
      scrolledNav: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll, { passive: true });
    this.updateScroll();
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.updateScroll);
  },
  methods: {
    updateScroll() {
      this.scrolledNav = window.scrollY > 50;
    },
    scrollToRules() {
      const el = document.getElementById("rules");
      if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
    },
    scrollToGroupStage() {
      const el = document.getElementById("group-stage");
      if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
    },
    scrollToPlayoff() {
      const el = document.getElementById("playoff");
      if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
    },
    scrollToTeams() {
      const el = document.getElementById("teams");
      if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
    },
  },
};
</script>

<style scoped>
.site-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 99;
  background-color: rgba(0, 0, 0, 0.8);
  color: #fff;
  transition:
    background-color 0.35s ease 0.08s,
    box-shadow 0.35s ease 0.08s;
}

.nav-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 12px;
  padding-bottom: 12px;
  transition: padding 0.35s ease 0.08s;
}

.branding h1 {
  margin: 0;
  line-height: 1;
  font-size: 24px;
  font-weight: 600;
}

.navigation {
  display: flex;
  align-items: center;
  gap: 24px;
  list-style: none;
  margin: 0;
  padding: 0;
}

.link {
  color: #fff;
  font-weight: 500;
  font-size: 14px;
  text-decoration: none;
  padding-bottom: 4px;
  border-bottom: 1px solid transparent;
  cursor: pointer;
  transition:
    color 0.2s ease,
    border-color 0.2s ease;
}

.link:hover {
  color: #5b5897;
  border-color: #686699;
}

.scrolled-nav {
  background-color: #000;
  box-shadow:
    0 4px 6px -1px rgba(0, 0, 0, 0.1),
    0 2px 4px -1px rgba(0, 0, 0, 0.06);
}

.scrolled-nav .nav-inner {
  padding-top: 8px;
  padding-bottom: 8px;
}
</style>
