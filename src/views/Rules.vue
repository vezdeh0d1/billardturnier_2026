<template>
  <section id="rules" class="section rules-section">
    <div class="container">
      <div class="branding">
        <h1>BILLIARDTURNIER 2026</h1>
      </div>

      <div class="rules-card">
        <p class="section-title">League Phase</p>

        <p class="rules-text">
          Nach langer Pause lassen wir das Bursen-Billardturnier wieder
          aufleben. In Teams von zwei Personen könnt ihr herausfinden, wer die
          besten Billardspieler*innen der Burse sind.
        </p>

        <div class="rules-block">
          <p class="rules-text">
            Ab dem <strong>20. April</strong> startet die erste Phase des
            Turniers: die
            <a
              href="#group-stage"
              class="inline-link"
              @click.prevent="scrollToGroupStage"
            >
              League Phase </a
            >. In dieser Phase vereinbart ihr als Teams eigenständig
            Spieltermine untereinander und tragt die Ergebnisse anschließend in
            die Tabelle beim Billardtisch ein.
          </p>

          <p class="rules-text">
            Ziel ist es, gegen jedes andere Team in einem
            <strong>Best-of-2</strong> anzutreten. Das bedeutet, dass maximal
            zwei Spiele gegen dasselbe Team gespielt werden. Entsprechend sind
            zum Beispiel die Ergebnisse <strong>2:0</strong>,
            <strong>1:1</strong> oder <strong>0:2</strong> möglich. Dabei gelten
            die Bursen-Billardregeln, die unten an der Bib aushängen.
          </p>

          <p class="rules-text">
            Am <strong>14. Mai</strong>, dem Ende der ersten Phase, wird anhand
            der Ergebnisse entschieden, wie die acht qualifizierten Teams für
            die
            <a
              href="#playoff"
              class="inline-link"
              @click.prevent="scrollToPlayoff"
            >
              Finalphase
            </a>
            gesetzt und auf <strong>Upper Bracket</strong> und
            <strong>Lower Bracket</strong> verteilt werden. Welche Position euer
            Team in der Finalphase erhält, erfahrt ihr am
            <strong>15. Mai</strong>.
          </p>
        </div>

        <div class="rules-block">
          <h2 class="section-title">Finalphase</h2>

          <p class="rules-text">
            Die Finalphase findet am <strong>16. Mai</strong> statt. Gespielt
            wird in einem angepassten
            <strong>Double-Elimination-System</strong>. Anhand der Punktzahl
            werden die acht qualifizierten Teams in
            <strong>Upper Bracket</strong> und <strong>Lower Bracket</strong>
            eingeteilt.
          </p>

          <p class="rules-text">
            Wer im Upper Bracket ein Spiel verliert, scheidet nicht sofort aus,
            sondern fällt ins Lower Bracket. Wer dagegen im Lower Bracket ein
            Spiel verliert, scheidet direkt aus dem Turnier aus.
          </p>

          <p class="rules-text">
            Alle Spiele der Finalphase werden im
            <strong>Best-of-1</strong>-Format gespielt. Nur das
            <strong>Grand Final</strong> wird im
            <strong>Best-of-3</strong>-Format ausgetragen.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Rules",
  methods: {
    scrollToGroupStage() {
      const el = document.getElementById("group-stage");
      if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
    },
    scrollToPlayoff() {
      const el = document.getElementById("playoff");
      if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
    },
  },
};
</script>

<style scoped>
.rules-section {
  padding-top: 120px;
}

.rules-card {
  background: linear-gradient(
    180deg,
    rgba(255, 255, 255, 0.05),
    rgba(255, 255, 255, 0.02)
  );
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 24px;
  padding: 40px;
  color: #fff;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  backdrop-filter: blur(8px);
}

.rules-block + .rules-block {
  margin-top: 32px;
}

.rules-text {
  margin-top: 18px;
  line-height: 1.8;
  font-size: 16px;
  color: rgba(255, 255, 255, 0.88);
}

.rules-outro {
  margin-top: 32px;
}

.rules-signature {
  margin-top: 20px;
}

.inline-link {
  color: #9a97e8;
  text-decoration: none;
  border-bottom: 1px solid transparent;
  transition:
    color 0.2s ease,
    border-color 0.2s ease;
}

.inline-link:hover {
  color: #c0bcff;
  border-color: #c0bcff;
}

.rules-list {
  margin-top: 18px;
  padding-left: 20px;
  color: rgba(255, 255, 255, 0.88);
}

.rules-list li {
  margin-bottom: 12px;
  line-height: 1.7;
}

.branding h1 {
  margin: 0;
  line-height: 1;
  font-size: 34px;
  font-weight: 600;
  padding: 0 0 40px 40px;
}

@media (max-width: 768px) {
  .rules-card {
    padding: 24px;
    border-radius: 18px;
  }

  .rules-text,
  .rules-list li {
    font-size: 15px;
  }
}
</style>
