<template>
  <section
    id="projekt"
    class="content-section project-section"
  >
    <!-- Einleitung der Projektsektion -->
    <p class="section-kicker">
      Portfolio
    </p>

    <div class="project-intro">
      <h2>
        Projekte, die man nicht nur ansehen,
        sondern ausprobieren kann.
      </h2>

      <p>
        Von meiner live veröffentlichten Mini-Bibliothek bis zu
        meinem IHK-Abschlussprojekt: Beide Anwendungen verbinden
        modernes Frontend-Design mit echter Backend-Logik und
        einer Datenbank.
      </p>
    </div>

    <!-- Projekt 01: Mini-Bibliothek -->
    <div class="project-card project-card--media project-card--live">
      <p class="project-number">
        01
      </p>

      <a
  class="project-preview project-preview--books"
  href="https://mini-bibliothek-fullstack.vercel.app/"
  target="_blank"
  rel="noopener noreferrer"
  aria-label="Mini-Bibliothek als Live-Projekt öffnen"
>
  <div class="project-preview-books" aria-hidden="true">
    <div class="preview-book preview-book--left"></div>
    <div class="preview-book preview-book--middle"></div>
    <div class="preview-book preview-book--right"></div>
    <div class="preview-book-shadow"></div>
  </div>

  <span class="project-live-badge">
    <span aria-hidden="true">●</span>
    Live
  </span>

  <span class="project-preview-hint">
    Projekt öffnen ↗
  </span>
</a>

      <div class="project-text">
        <h3 class="project-title-with-icon">
          <span
            class="project-title-icon"
            aria-hidden="true"
          >
            📚
          </span>

          Mini-Bibliothek
        </h3>

        <p>
          Die Mini-Bibliothek war mein erstes selbstständig
          entwickeltes Projekt während meines Praktikums und
          damit einer meiner ersten großen Schritte in der
          Fullstack-Entwicklung.
        </p>

        <p>
          Aus der ursprünglichen Buchverwaltung entstand später
          eine responsive Anwendung mit Benutzerkonten, Rollen,
          Favoriten, Bewertungen und einer Anbindung an die
          Open Library API. Für mein Portfolio habe ich das
          Projekt als Live-Demo veröffentlicht.
        </p>

        <div class="project-tags project-tags-with-icons">
          <span
            v-for="tag in fullstackTags"
            :key="tag.name"
            class="project-tech-tag"
          >
            <img
              :src="tag.icon"
              alt=""
              aria-hidden="true"
              loading="lazy"
            >

            {{ tag.name }}
          </span>
        </div>

        <div class="project-actions">
          <a
            href="https://mini-bibliothek-fullstack.vercel.app/"
            class="button primary-button"
            target="_blank"
            rel="noopener noreferrer"
          >
            Live-Demo öffnen
          </a>

          <a
            href="https://github.com/if1991/mini-bibliothek-fullstack"
            class="button secondary-button"
            target="_blank"
            rel="noopener noreferrer"
          >
            Code auf GitHub
          </a>
        </div>

        <p class="project-demo-note">
          Hinweis: Beim ersten Öffnen kann das
          Backend einige Sekunden zum Starten benötigen.
        </p>
      </div>
    </div>

    <!-- Projekt 02: Fleet Manager -->

    <div class="project-card project-card--media project-card--fleet">
      <p class="project-number">
        02
      </p>

      <!-- Vorschau des Abschlussprojekts -->
      <a
  class="project-preview project-preview--fleet-art"
  href="#fleet-case-study"
  aria-label="Zur ausführlichen Fleet-Manager-Case-Study springen"
>
  <div
    class="project-preview-fleet-visual"
    aria-hidden="true"
  >
    <div class="fleet-road"></div>

    <div class="fleet-car-card">
      <span class="fleet-car-emoji">🚗</span>
      <span class="fleet-car-title">Fleet Manager</span>
      <span class="fleet-car-subtitle">Fuhrpark, Buchungen, Wartung</span>
    </div>
  </div>

  <span class="project-case-badge">
    <span aria-hidden="true">◆</span>
    Case Study
  </span>

  <span class="project-preview-hint">
    Case Study ansehen ↓
  </span>
</a>

      <!-- Kurzbeschreibung und Technologien -->
      <div class="project-text">
        <h3 class="project-title-with-icon">
          <span
            class="project-title-icon"
            aria-hidden="true"
          >
            🚗
          </span>

          Fleet Manager
        </h3>

        <p>
          Der Fleet Manager ist mein IHK-Abschlussprojekt und
          bildet die zentrale Verwaltung eines betrieblichen
          Fuhrparks als Fullstack-Webanwendung ab.
        </p>

        <p>
          Die Anwendung verbindet Fahrzeug- und Buchungsverwaltung
          mit Wartungen, Sperren, Schadenmeldungen, Rollenlogik,
          Archivierung und fahrzeugbezogenen Auswertungen.
          Fachliche Regeln wie Überschneidungsprüfungen und
          Statuswechsel werden zusätzlich serverseitig abgesichert.
        </p>

        <div class="project-tags project-tags-with-icons">
          <span
            v-for="tag in fullstackTags"
            :key="tag.name"
            class="project-tech-tag"
          >
            <img
              :src="tag.icon"
              alt=""
              aria-hidden="true"
              loading="lazy"
            >

            {{ tag.name }}
          </span>
        </div>

        <div class="project-actions">
  <a
    href="#fleet-case-study"
    class="button primary-button"
  >
    Case Study ansehen
  </a>

  <span
    class="button secondary-button project-button--disabled"
    aria-label="Quellcode derzeit nicht öffentlich verfügbar"
  >
    Quellcode derzeit privat
  </span>
</div>

<p class="project-code-note">
  Der vollständige Quellcode wird aktuell nicht öffentlich bereitgestellt.
</p>

      </div>
    </div>


    <!-- Einleitung zur Fleet-Manager-Case-Study -->
    <div
       id="fleet-case-study"
       class="case-study-heading"
      >
      <p class="section-kicker">
        Case Study
      </p>

      <h3>
        Ein Blick in die Anwendung.
      </h3>

      <p>
        Die folgenden Ausschnitte zeigen zentrale Bereiche
        des Fleet Managers: vom Dashboard über Fahrzeug- und
        Buchungsverwaltung bis hin zu Schadenmeldungen,
        Archiv, Auswertung und Rollenlogik.
      </p>
    </div>


       <!-- Einzelne Schritte der Fleet-Manager-Case-Study -->
        <div
         class="case-study-showcase"
         role="region"
         aria-label="Fleet Manager Case Study"
        >


      <article
        v-for="(item, index) in caseStudyItems"
        :key="item.title"
        :ref="(element) => setCaseStudyRef(element, index)"
        class="case-study-step"
        :class="{
          'case-study-step--reverse': index % 2 === 1,
        }"
      >
        <div class="case-study-copy reveal-from-left">
          <p class="case-study-number">
            {{ item.number }}
          </p>

          <h4>
            {{ item.title }}
          </h4>

          <p>
            {{ item.text }}
          </p>

          <ul>
            <li
              v-for="point in item.points"
              :key="point"
            >
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
          <img
            :src="item.image"
            :alt="item.alt"
            loading="lazy"
          >

          <span class="case-study-image-hint">
            Bild vergrößern
          </span>
        </button>
      </article>
    </div>

    <!-- Datenschutzhinweis zu den Demo-Daten -->
    <div class="case-study-privacy-note">
      <h4 class="privacy-note-title">
        <span
          class="privacy-note-icon"
          aria-hidden="true"
        >
          !
        </span>

        Der Schutz personenbezogener Daten ist mir
        besonders wichtig.
      </h4>

      <p>
        Deshalb wurden für die Präsentation des Projekts
        ausschließlich Demo-Daten verwendet. Alle in den
        Screenshots gezeigten Fahrzeuge, Kennzeichen,
        Schadenbilder, Namen und E-Mail-Adressen wurden
        zu Präsentationszwecken erstellt.
      </p>

      <p>
        Es werden keine echten Kundendaten, Betriebsdaten
        oder personenbezogenen Daten dargestellt.
        Ausgenommen davon sind mein eigener Name sowie
        meine eigene Kontaktadresse.
      </p>
    </div>

    <!-- Lightbox für die vergrößerte Screenshot-Ansicht -->
    <div
      v-if="selectedImage"
      class="image-lightbox"
      role="dialog"
      aria-modal="true"
      :aria-label="`${selectedImage.title} vergrößert`"
      @click.self="closeImage"
    >
      <button
        class="image-lightbox-close"
        type="button"
        aria-label="Vergrößerte Ansicht schließen"
        @click="closeImage"
      >
        Schließen
      </button>

      <div class="image-lightbox-content">
        <img
          :src="selectedImage.image"
          :alt="selectedImage.alt"
        >
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import {
  onBeforeUnmount,
  onMounted,
  ref,
} from 'vue'

/* Typen für Technologien und Case-Study-Inhalte */
type ProjectTag = {
  name: string
  icon: string
}

type CaseStudyItem = {
  number: string
  title: string
  text: string
  image: string
  alt: string
  points: string[]
}

/* Technologien der beiden Fullstack-Projekte */
const fullstackTags: ProjectTag[] = [
  {
    name: 'Vue 3',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg',
  },
  {
    name: 'TypeScript',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg',
  },
  {
    name: 'Pinia',
    icon: 'https://pinia.vuejs.org/logo.svg',
  },
  {
    name: 'Vuetify',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuetify/vuetify-original.svg',
  },
  {
    name: 'Node.js',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-original.svg',
  },
  {
    name: 'GraphQL',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/graphql/graphql-plain.svg',
  },
  {
    name: 'MongoDB',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mongodb/mongodb-original.svg',
  },
]

/* Inhalte der Fleet-Manager-Case-Study */
const caseStudyItems: CaseStudyItem[] = [
  {
    number: '01',
    title: 'Dashboard und Fahrzeugkalender',
    text:
      'Die Startseite bietet einen schnellen Einstieg in die Anwendung. ' +
      'Der Kalender zeigt, welche Fahrzeuge in welchem Zeitraum gebucht ' +
      'sind, ohne dabei Nutzernamen öffentlich anzuzeigen.',
    image: '/case-study/01dashboard.png',
    alt:
      'Dashboard des Fleet Managers mit Kalender und ' +
      'Dokumentenerinnerungen',
    points: [
      'zentrale Einstiegsseite mit Schnellzugriffen',
      'Fahrzeugbelegung ohne Anzeige von Nutzernamen',
      'Hinweise auf ablaufende Dokumente',
    ],
  },
  {
    number: '02',
    title: 'Fahrzeugverwaltung mit Statuslogik',
    text:
      'Admins können Fahrzeuge anlegen und relevante Stammdaten ' +
      'bearbeiten. Der Fahrzeugstatus bildet ab, ob ein Fahrzeug ' +
      'verfügbar, gebucht, gesperrt oder in Wartung ist.',
    image: '/case-study/02-vehicles.png',
    alt:
      'Fahrzeugübersicht mit mehreren Fahrzeugkarten ' +
      'und Statusanzeigen',
    points: [
      'Fahrzeugkarten mit Status, Standort und Kilometerstand',
      'Admin-Verwaltung für relevante Fahrzeugdaten',
      'Grundlage für Buchungs- und Wartungslogik',
    ],
  },
  {
    number: '03',
    title: 'Buchungen und Verfügbarkeitsprüfung',
    text:
      'Buchungen werden durch den Admin geprüft und genehmigt. ' +
      'Die Anwendung verhindert serverseitig, dass ein Fahrzeug ' +
      'im gleichen Zeitraum mehrfach gebucht wird.',
    image: '/case-study/03-bookings.png',
    alt:
      'Buchungsübersicht des Fleet Managers mit ' +
      'mehreren Buchungskarten',
    points: [
      'Buchungen werden durch Admins geprüft und genehmigt',
      'Überschneidungen werden serverseitig verhindert',
      'ein Fahrzeug kann nicht gleichzeitig doppelt gebucht werden',
    ],
  },
  {
    number: '04',
    title: 'Check-in, Check-out und Kilometerstand',
    text:
      'Beim Check-out und Check-in werden Kilometerstände erfasst ' +
      'und geprüft. Nach der Rückgabe wird der Fahrzeugkilometerstand ' +
      'aktualisiert und die Änderung bleibt nachvollziehbar.',
    image: '/case-study/04-checkout.png.png',
    alt:
      'Check-in oder Check-out im Fleet Manager ' +
      'mit Kilometerstand',
    points: [
      'Kilometerstand wird bei der Fahrzeugrückgabe aktualisiert',
      'unplausible Kilometerwerte werden verhindert',
      'Änderungen bleiben fahrzeugbezogen nachvollziehbar',
    ],
  },
  {
    number: '05',
    title: 'Schadenmeldungen im Admin-Bereich',
    text:
      'Schäden können gemeldet, geprüft und verwaltet werden. ' +
      'Admins können den Status bearbeiten und so nachvollziehen, ' +
      'welche Fahrzeuge Aufmerksamkeit benötigen.',
    image: '/case-study/05-damage-reports.png',
    alt:
      'Schadenmeldungen im Fleet Manager ' +
      'mit Statusverwaltung',
    points: [
      'Status OFFEN, IN PRÜFUNG und GESCHLOSSEN',
      'Admin kann Schadenmeldungen prüfen und bearbeiten',
      'normale Nutzer sehen nur eigene Meldungen',
    ],
  },
  {
    number: '06',
    title: 'Archiv und Nachvollziehbarkeit',
    text:
      'Abgeschlossene oder gelöschte Vorgänge werden archiviert. ' +
      'Dadurch bleibt die aktive Oberfläche übersichtlich, während ' +
      'ältere Buchungen und Fahrzeuge nachvollziehbar bleiben.',
    image: '/case-study/06-archive.png',
    alt:
      'Archivansicht des Fleet Managers mit archivierten ' +
      'Buchungen und Fahrzeugen',
    points: [
      'Archiv für alte Buchungen und gesperrte Fahrzeuge',
      'Trennung von aktiven und abgeschlossenen Daten',
      'bessere Übersicht im laufenden Betrieb',
    ],
  },
  {
    number: '07',
    title: 'Rollen, Freigaben und Datenschutz',
    text:
      'Die Anwendung unterscheidet zwischen normalen Nutzern und ' +
      'Admins. Neue Accounts erhalten einen Status und können durch ' +
      'Admins geprüft, freigegeben oder gesperrt werden. Zugriffe ' +
      'werden zusätzlich serverseitig im Backend geprüft.',
    image: '/case-study/07-users.png',
    alt:
      'Nutzerverwaltung im Admin-Bereich ' +
      'des Fleet Managers',
    points: [
      'normale Nutzer sehen nur eigene Buchungen, Schäden und Profildaten',
      'Admin-Bereiche sind zusätzlich serverseitig geschützt',
      'Passwörter werden als Hash gespeichert',
    ],
  },
  {
    number: '08',
    title: 'Kostenbericht und Auswertungen',
    text:
      'Auswertungen fassen fahrzeugbezogene Kosten zusammen ' +
      'und helfen dabei, Daten nicht nur zu speichern, ' +
      'sondern nutzbar zu machen.',
    image: '/case-study/08-cost-report.png',
    alt:
      'Kostenbericht des Fleet Managers ' +
      'mit Kostenübersicht',
    points: [
      'Kostenübersicht nach Fahrzeug',
      'technische Basis für Exporte',
      'Auswertung relevanter Betriebsdaten',
    ],
  },
]

/* Zustand der Screenshot-Lightbox */
const selectedImage = ref<CaseStudyItem | null>(null)

/* Elemente und Observer für die Scroll-Animationen */
const caseStudyElements: Element[] = []
let observer: IntersectionObserver | null = null

/* Speichert die gerenderten Case-Study-Elemente */
function setCaseStudyRef(
  element: Element | unknown,
  index: number
): void {
  if (element instanceof Element) {
    caseStudyElements[index] = element
  }
}

/* Öffnet einen Screenshot in der Lightbox */
function openImage(item: CaseStudyItem): void {
  selectedImage.value = item
  document.body.classList.add('lightbox-open')
}

/* Schließt die Lightbox */
function closeImage(): void {
  selectedImage.value = null
  document.body.classList.remove('lightbox-open')
}

/* Ermöglicht das Schließen der Lightbox über Escape */
function handleKeydown(event: KeyboardEvent): void {
  if (
    event.key === 'Escape' &&
    selectedImage.value
  ) {
    closeImage()
  }
}

/* Aktiviert Animationen und Tastatursteuerung */
onMounted(() => {
  window.addEventListener(
    'keydown',
    handleKeydown
  )

  if (!('IntersectionObserver' in window)) {
    caseStudyElements.forEach((element) => {
      element.classList.add('is-visible')
    })

    return
  }

  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (!entry.isIntersecting) {
          return
        }

        entry.target.classList.add('is-visible')
        observer?.unobserve(entry.target)
      })
    },
    {
      threshold: 0.18,
      rootMargin: '0px 0px -80px 0px',
    }
  )

  caseStudyElements.forEach((element) => {
    observer?.observe(element)
  })
})

/* Entfernt Listener und Klassen beim Verlassen der Seite */
onBeforeUnmount(() => {
  observer?.disconnect()

  window.removeEventListener(
    'keydown',
    handleKeydown
  )

  document.body.classList.remove(
    'lightbox-open'
  )
})
</script>

