<template>
  <section class="content-section project-section" id="projekt">
    <p class="section-kicker">Portfolio</p>

    <div class="project-intro">
      <h2>Mein Abschlussprojekt als technische Case Study.</h2>

      <p>
        Der Fleet Manager verbindet Benutzeroberfläche, Datenmodell,
        API-Anbindung, Validierung und fachliche Logik in einer
        Fullstack-Webanwendung.
      </p>
    </div>

    <div class="project-card">
      <div class="project-text">
        <p class="project-number">01</p>

        <h3>Fleet Manager</h3>

        <p>
          Eine Fuhrparkverwaltung zur Verwaltung von Fahrzeugen, Buchungen,
          Wartungen, Sperren, Schadenmeldungen und Auswertungen.
        </p>

        <div class="project-tags">
          <span>Vue 3</span>
          <span>TypeScript</span>
          <span>Pinia</span>
          <span>Vuetify</span>
          <span>Node.js</span>
          <span>GraphQL</span>
          <span>MongoDB</span>
        </div>

        <div class="project-actions">
          <a
            href="https://github.com/if1991/fleet-manager-abschlussprojekt"
            class="button primary-button"
            target="_blank"
            rel="noopener noreferrer"
          >
            Code auf GitHub ansehen
          </a>

          <a href="#kontakt" class="button secondary-button">
            Kontakt aufnehmen
          </a>
        </div>
      </div>

      <div class="project-details">
        <h3>Schwerpunkte</h3>

        <ul>
          <li>Frontend mit Formularen, Statusanzeigen und Listenansichten</li>
          <li>Buchungslogik mit Prüfung von Fahrzeugstatus und Zeiträumen</li>
          <li>Backend-Funktionen mit Apollo GraphQL und MongoDB</li>
          <li>Rollen- und Berechtigungslogik für unterschiedliche Nutzer</li>
          <li>Fehleranalyse, Validierung und technische Dokumentation</li>
        </ul>
      </div>
    </div>

    <div class="case-study-heading">
      <p class="section-kicker">Case Study</p>

      <h3>Ein Blick in die Anwendung.</h3>

      <p>
        Die folgenden Ausschnitte zeigen zentrale Bereiche des Fleet Managers:
        vom Dashboard über Fahrzeug- und Buchungsverwaltung bis hin zu
        Schadenmeldungen, Archiv, Auswertung und Rollenlogik.
      </p>
    </div>

    <div class="case-study-showcase" aria-label="Fleet Manager Case Study">
      <article
        v-for="(item, index) in caseStudyItems"
        :key="item.title"
        :ref="(element) => setCaseStudyRef(element, index)"
        class="case-study-step"
        :class="{ 'case-study-step--reverse': index % 2 === 1 }"
      >
        <div class="case-study-copy reveal-from-left">
          <p class="case-study-number">{{ item.number }}</p>

          <h4>{{ item.title }}</h4>

          <p>{{ item.text }}</p>

          <ul>
            <li v-for="point in item.points" :key="point">
              {{ point }}
            </li>
          </ul>
        </div>

        <button
          class="case-study-image-card reveal-from-right"
          type="button"
          :aria-label="`${item.title} als großes Bild öffnen`"
          @click="openImage(item)"
        >
          <img :src="item.image" :alt="item.alt" loading="lazy" />

          <span class="case-study-image-hint">
            Bild vergrößern
          </span>
        </button>
      </article>
    </div>

    <div class="case-study-privacy-note">
      <h4>Der Schutz personenbezogener Daten ist mir besonders wichtig,</h4>

      <p>
        Deshalb wurden für die
    Präsentation des Projekts ausschließlich Demo-Daten verwendet. Alle in den
    Screenshots gezeigten Fahrzeuge, Kennzeichen, Schadenbilder, Namen und
    E-Mail-Adressen wurden zu Präsentationszwecken erstellt. Es werden keine
    echten Kundendaten, Betriebsdaten oder personenbezogenen Daten dargestellt.
    Ausgenommen davon sind mein eigener Name sowie meine eigene Kontaktadresse.
      </p>
    </div>

    <div
      v-if="selectedImage"
      class="image-lightbox"
      role="dialog"
      aria-modal="true"
      :aria-label="`${selectedImage.title} vergrößert`"
      @click.self="closeImage"
    >
      <button class="image-lightbox-close" type="button" @click="closeImage">
        Schließen
      </button>

      <div class="image-lightbox-content">
        <img :src="selectedImage.image" :alt="selectedImage.alt" />
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue'

type CaseStudyItem = {
  number: string
  title: string
  text: string
  image: string
  alt: string
  points: string[]
}

const caseStudyItems: CaseStudyItem[] = [
  {
    number: '01',
    title: 'Dashboard und Fahrzeugkalender',
    text: 'Die Startseite bietet einen schnellen Einstieg in die Anwendung. Der Kalender zeigt, welche Fahrzeuge in welchem Zeitraum gebucht sind, ohne dabei Nutzernamen öffentlich anzuzeigen.',
    image: '/case-study/01dashboard.png',
    alt: 'Dashboard des Fleet Managers mit Kalender und Dokumentenerinnerungen',
    points: [
      'zentrale Einstiegsseite mit Schnellzugriffen',
      'Fahrzeugbelegung ohne Anzeige von Nutzernamen',
      'Hinweise auf ablaufende Dokumente',
    ],
  },
  {
    number: '02',
    title: 'Fahrzeugverwaltung mit Statuslogik',
    text: 'Admins können Fahrzeuge anlegen und relevante Stammdaten bearbeiten. Der Fahrzeugstatus bildet ab, ob ein Fahrzeug verfügbar, gebucht, gesperrt oder in Wartung ist.',
    image: '/case-study/02-vehicles.png',
    alt: 'Fahrzeugübersicht mit mehreren Fahrzeugkarten und Statusanzeigen',
    points: [
      'Fahrzeugkarten mit Status, Standort und Kilometerstand',
      'Admin-Verwaltung für relevante Fahrzeugdaten',
      'Grundlage für Buchungs- und Wartungslogik',
    ],
  },
  {
    number: '03',
    title: 'Buchungen und Verfügbarkeitsprüfung',
    text: 'Buchungen werden durch den Admin geprüft und genehmigt. Die Anwendung verhindert serverseitig, dass ein Fahrzeug im gleichen Zeitraum mehrfach gebucht wird.',
    image: '/case-study/03-bookings.png',
    alt: 'Buchungsübersicht des Fleet Managers mit mehreren Buchungskarten',
    points: [
      'Buchungen werden durch Admins geprüft und genehmigt',
      'Überschneidungen werden serverseitig verhindert',
      'ein Fahrzeug kann nicht gleichzeitig doppelt gebucht werden',
    ],
  },
  {
    number: '04',
    title: 'Check-in, Check-out und Kilometerstand',
    text: 'Beim Check-out und Check-in werden Kilometerstände erfasst und geprüft. Nach der Rückgabe wird der Fahrzeugkilometerstand aktualisiert und die Änderung bleibt nachvollziehbar.',
    image: '/case-study/04-checkout.png.png',
    alt: 'Check-in oder Check-out im Fleet Manager mit Kilometerstand',
    points: [
      'Kilometerstand wird bei der Fahrzeugrückgabe aktualisiert',
      'unplausible Kilometerwerte werden verhindert',
      'Änderungen bleiben fahrzeugbezogen nachvollziehbar',
    ],
  },
  {
    number: '05',
    title: 'Schadenmeldungen im Admin-Bereich',
    text: 'Schäden können gemeldet, geprüft und verwaltet werden. Admins können den Status bearbeiten und so nachvollziehen, welche Fahrzeuge Aufmerksamkeit benötigen.',
    image: '/case-study/05-damage-reports.png',
    alt: 'Schadenmeldungen im Fleet Manager mit Statusverwaltung',
    points: [
      'Status OFFEN, IN PRÜFUNG und GESCHLOSSEN',
      'Admin kann Schadenmeldungen prüfen und bearbeiten',
      'normale Nutzer sehen nur eigene Meldungen',
    ],
  },
  {
    number: '06',
    title: 'Archiv und Nachvollziehbarkeit',
    text: 'Abgeschlossene oder gelöschte Vorgänge werden archiviert. Dadurch bleibt die aktive Oberfläche übersichtlich, während ältere Buchungen und Fahrzeuge nachvollziehbar bleiben.',
    image: '/case-study/06-archive.png',
    alt: 'Archivansicht des Fleet Managers mit archivierten Buchungen und Fahrzeugen',
    points: [
      'Archiv für alte Buchungen und gesperrte Fahrzeuge',
      'Trennung von aktiven und abgeschlossenen Daten',
      'bessere Übersicht im laufenden Betrieb',
    ],
  },
  {
    number: '07',
    title: 'Rollen, Freigaben und Datenschutz',
    text: 'Die Anwendung unterscheidet zwischen normalen Nutzern und Admins. Neue Accounts erhalten einen Status und können durch Admins geprüft, freigegeben oder gesperrt werden. Zugriffe werden nicht nur in der Oberfläche, sondern serverseitig im Backend geprüft.',
    image: '/case-study/07-users.png',
    alt: 'Nutzerverwaltung im Admin-Bereich des Fleet Managers',
    points: [
      'normale Nutzer sehen nur eigene Buchungen, Schäden und Profildaten',
      'Admin-Bereiche sind zusätzlich serverseitig geschützt',
      'Passwörter werden als Hash gespeichert',
    ],
  },
  {
    number: '08',
    title: 'Kostenbericht und Auswertungen',
    text: 'Auswertungen fassen fahrzeugbezogene Kosten zusammen und helfen dabei, Daten nicht nur zu speichern, sondern nutzbar zu machen.',
    image: '/case-study/08-cost-report.png',
    alt: 'Kostenbericht des Fleet Managers mit Kostenübersicht',
    points: [
      'Kostenübersicht nach Fahrzeug',
      'technische Basis für Exporte',
      'Auswertung relevanter Betriebsdaten',
    ],
  },
]

const selectedImage = ref<CaseStudyItem | null>(null)

let observer: IntersectionObserver | null = null
const caseStudyElements: Element[] = []

function setCaseStudyRef(element: Element | unknown, index: number): void {
  if (element instanceof Element) {
    caseStudyElements[index] = element
  }
}

function openImage(item: CaseStudyItem): void {
  selectedImage.value = item
  document.body.classList.add('lightbox-open')
}

function closeImage(): void {
  selectedImage.value = null
  document.body.classList.remove('lightbox-open')
}

onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('is-visible')
        }
      })
    },
    {
      threshold: 0.18,
      rootMargin: '0px 0px -80px 0px',
    },
  )

  caseStudyElements.forEach((element) => observer?.observe(element))
})

onBeforeUnmount(() => {
  observer?.disconnect()
  document.body.classList.remove('lightbox-open')
})
</script>