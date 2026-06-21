<template>
  <nav class="navigation-bar" aria-label="Hauptnavigation">
    <a href="#top" class="navigation-logo">Inga Faber</a>

    <div class="navigation-links">
      <a href="#about">Über mich</a>
      <a href="#skills">Skills</a>
      <a href="#projekt">Projekte</a>
      <a href="#kontakt">Kontakt</a>

      <button class="theme-toggle" type="button" @click="toggleTheme">
        {{ isDarkMode ? '☀ Light' : '🌙 Dark' }}
      </button>
      <button class="accessibility-button" type="button" @click="decreaseFontSize">
  A−
</button>

<button class="accessibility-button" type="button" @click="increaseFontSize">
  A+
</button>

<button class="accessibility-button" type="button" @click="toggleContrast">
  Kontrast
</button>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'

const isDarkMode = ref(false)
const fontSizeLevel = ref(0)
const isHighContrast = ref(false)

function applyTheme(): void {
  if (isDarkMode.value) {
    document.documentElement.classList.add('dark-mode')
    localStorage.setItem('theme', 'dark')
  } else {
    document.documentElement.classList.remove('dark-mode')
    localStorage.setItem('theme', 'light')
  }
}

function toggleTheme(): void {
  isDarkMode.value = !isDarkMode.value
  applyTheme()
}
function applyAccessibilitySettings(): void {
  document.documentElement.classList.remove('font-large')
  document.documentElement.classList.remove('font-xlarge')

  if (fontSizeLevel.value === 1) {
    document.documentElement.classList.add('font-large')
  }

  if (fontSizeLevel.value === 2) {
    document.documentElement.classList.add('font-xlarge')
  }

  if (isHighContrast.value) {
    document.documentElement.classList.add('high-contrast')
  } else {
    document.documentElement.classList.remove('high-contrast')
  }

  localStorage.setItem('fontSizeLevel', String(fontSizeLevel.value))
  localStorage.setItem('highContrast', String(isHighContrast.value))
}

function increaseFontSize(): void {
  if (fontSizeLevel.value < 2) {
    fontSizeLevel.value++
  }

  applyAccessibilitySettings()
}

function decreaseFontSize(): void {
  if (fontSizeLevel.value > 0) {
    fontSizeLevel.value--
  }

  applyAccessibilitySettings()
}

function toggleContrast(): void {
  isHighContrast.value = !isHighContrast.value
  applyAccessibilitySettings()
}

onMounted(() => {
  const savedTheme = localStorage.getItem('theme')
  const savedFontSizeLevel = localStorage.getItem('fontSizeLevel')
  const savedHighContrast = localStorage.getItem('highContrast')

  if (savedTheme === 'dark') {
    isDarkMode.value = true
  }

  applyTheme()
  if (savedFontSizeLevel !== null) {
  fontSizeLevel.value = Number(savedFontSizeLevel)
}

if (savedHighContrast === 'true') {
  isHighContrast.value = true
}

applyAccessibilitySettings()
})
</script>