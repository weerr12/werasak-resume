<script setup lang="ts">
interface Education {
  institution: string
  degree: string
  period: string
  url: string
}

const education: Education[] = [
  {
    institution: 'Chiang Mai University',
    degree: 'Bachelor of Engineering in Computer Engineering',
    period: '2022 - 2025',
    url: 'https://www.cmu.ac.th/en/home',
  },
]
</script>

<template>
  <section id="education">
    <h2 class="text-3xl font-bold text-gray-800 mb-5">Education</h2>
    <hr class="border-t border-gray-300 w-full mb-5" />

    <div class="space-y-8 mb-5">
      <div v-for="edu in education" :key="edu.institution">
        <h3 class="text-lg font-bold text-gray-800">
          {{ edu.degree }} at
          <a
            :href="edu.url"
            target="_blank"
            class="text-blue-600 hover:text-blue-800 hover:underline transition-colors"
          >
            {{ edu.institution }}
          </a>
        </h3>

        <p class="text-sm text-gray-500 mb-3">{{ edu.period }}</p>
      </div>
    </div>

    <hr class="border-t border-gray-300 w-full mb-5" />
  </section>
</template>
