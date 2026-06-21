<template>
  <section class="content-section skills-section" id="skills">
    <p class="section-kicker">Skills & Inhalte</p>

    <div class="skills-heading">
      <h2>Technologien und Inhalte aus meiner Umschulung.</h2>

      <p>
        Während meiner Umschulung und im Praktikum konnte ich verschiedene
        Bereiche der Anwendungsentwicklung kennenlernen — von Webentwicklung
        über Datenbanken bis hin zu Fehleranalyse, Dokumentation und
        Projektarbeit.
      </p>
    </div>

    <div
  class="skills-grid"
  :class="{ 'skills-grid--all-open': openedCardIds.length === skillCards.length }"
>
      <article
        v-for="card in skillCards"
        :key="card.id"
        class="skill-card"
        :class="{ 'skill-card--open': openedCardIds.includes(card.id) }"
      >
        <div class="skill-card-header">
          <div>
            <p class="skill-card-kicker">{{ card.kicker }}</p>
            <h3>{{ card.title }}</h3>
          </div>

          <button
            class="skill-toggle-button"
            type="button"
            :aria-expanded="openedCardIds.includes(card.id)"
            :aria-controls="`${card.id}-details`"
            @click="toggleCard(card.id)"
          >
            <span v-if="openedCardIds.includes(card.id)">−</span>
            <span v-else>+</span>
          </button>
        </div>

        <ul class="skill-short-list">
          <li v-for="item in card.shortItems" :key="item">
            {{ item }}
          </li>
        </ul>

        <div
          v-if="openedCardIds.includes(card.id)"
          :id="`${card.id}-details`"
          class="skill-card-details"
        >
          <p>
            {{ card.description }}
          </p>

          <ul>
            <li v-for="detail in card.details" :key="detail">
              {{ detail }}
            </li>
          </ul>
        </div>
      </article>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

type SkillCard = {
  id: string
  kicker: string
  title: string
  shortItems: string[]
  description: string
  details: string[]
}

const openedCardIds = ref<string[]>([])

const skillCards: SkillCard[] = [
  {
    id: 'umschulung',
    kicker: 'Theorie & Grundlagen',
    title: 'Inhalte der Umschulung',
    shortItems: [
      'OOP und C-Grundlagen',
      'SQL und Datenbanken',
      'Netzwerke und Hardware',
      'Datenschutz und IT-Sicherheit',
    ],
    description:
      'In der Umschulung habe ich vor allem grundlegende Themen der Informatik, Softwareentwicklung und IT kennengelernt. Viele Inhalte wurden als Grundlagen vermittelt und bilden für mich die Basis, auf der ich weiter aufbauen möchte.',
    details: [
      'Grundlagen der objektorientierten Programmierung',
      'C-Grundlagen und allgemeine Programmierlogik',
      'SQL-Abfragen und Grundlagen der Datenbankmodellierung',
      'Netzwerkgrundlagen und Hardware-Basiswissen',
      'Datenschutz, IT-Sicherheit und rechtliche Grundlagen',
      'Qualitätsmanagement, Mitarbeiterführung und Marketing-Grundlagen',
    ],
  },
  {
    id: 'praktikum',
    kicker: 'Praxis & Projekt',
    title: 'Inhalte aus dem Praktikum',
    shortItems: [
      'Vue 3 und TypeScript',
      'GraphQL und Apollo',
      'MongoDB und Mongoose',
      'Projektarbeit im Abschlussprojekt',
    ],
    description:
      'Im Praktikum und im Abschlussprojekt konnte ich praktische Erfahrung mit moderner Webentwicklung sammeln. Besonders spannend war für mich die Verbindung aus Benutzeroberfläche, Backend-Logik und Datenbank.',
    details: [
      'Arbeiten mit Vue 3, TypeScript und Komponentenstruktur',
      'Verwendung von Pinia und Vuetify im Frontend',
      'Anbindung an eine GraphQL-API mit Apollo',
      'Backend-Grundlagen mit Node.js, GraphQL und MongoDB',
      'Umsetzung von Formularen, Listenansichten und Statusanzeigen',
      'Fehlersuche und schrittweise Verbesserung von Funktionen',
    ],
  },
  {
    id: 'arbeitsweise',
    kicker: 'Lessons Learned',
    title: 'Arbeitsweise',
    shortItems: [
      'strukturiertes Nacharbeiten',
      'Fehleranalyse',
      'Recherche',
      'KI-gestützte Unterstützung',
    ],
    description:
      'Während der Projektarbeit habe ich gemerkt, wie wichtig es ist, Probleme ruhig und Schritt für Schritt zu analysieren. Ich arbeite gerne mit Beispielen, Recherche, Dokumentation und unterstützenden Tools, um Lösungen besser zu verstehen.',
    details: [
      'Aufgaben in kleinere Schritte zerlegen',
      'Fehlermeldungen lesen und Ursachen eingrenzen',
      'technische Themen recherchieren und nacharbeiten',
      'KI-Tools unterstützend für Verständnis, Codeanalyse und Ideensammlung nutzen',
      'Ergebnisse testen, vergleichen und bei Bedarf überarbeiten',
      'offen bleiben für Feedback und Verbesserung',
    ],
  },
]
function toggleCard(cardId: string): void {
  if (openedCardIds.value.includes(cardId)) {
    openedCardIds.value = openedCardIds.value.filter((id) => id !== cardId)
    return
  }

  openedCardIds.value.push(cardId)
}
</script>