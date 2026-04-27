<script setup lang="ts">
interface Experience {
  company: string
  companyUrl: string
  role: string
  period: string
  duration: string
  summary: string
  accomplishments: string[]
}

const experiences: Experience[] = [
  {
    company: 'Paiduaykanmai',
    companyUrl: 'https://pdkm.tech/th/contact-us',
    role: 'Frontend Developer Internship ',
    period: 'Jun 2025 – Oct 2025',
    duration: '4 months',
    summary: 'Contributed to a team building scalable microservices.',
    accomplishments: [
      'Systematized source code ingestion by architecting a GitHub OAuth 2.0 module, eliminating 100% of manual uploads and streamlining Al-driven analysis for the Cortex Al project.',
      'Designed a scalable design system of 31+ reusable components using CVA and Tailwind CSS v4, reducing frontend development lead time and ensuring cross-product UI consistency.',
      'Accelerated architectural auditing by developing an interactive analytics dashboard with ECharts, providing engineers with real-time visibility into codebase health.',
      'Optimized AI-to-Code synchronization pipelines, achieving 100% architectural integrity between generated outputs and production-ready codebases.',
    ],
  },
]
</script>

<template>
  <section id="experience">
    <h2 class="text-3xl font-bold text-gray-800 mb-5">Work Experience</h2>
    <hr class="border-t border-gray-300 w-full mb-5" />

    <div class="space-y-8 mb-5">
      <div v-for="exp in experiences" :key="exp.company">
        <h3 class="text-lg font-bold text-gray-800">
          {{ exp.role }} at
          <a :href="exp.companyUrl" target="_blank" class="text-blue-600 hover:underline">
            {{ exp.company }}
          </a>
        </h3>

        <p class="text-sm text-gray-500 mb-3">{{ exp.period }} ({{ exp.duration }})</p>
        <div class="text-sm text-gray-500 mb-5">Accomplishments</div>
        <ul class="list-disc list-outside pl-8 space-y-2 text-sm text-gray-500">
          <li v-for="(item, i) in exp.accomplishments" :key="i">
            {{ item }}
          </li>
        </ul>
      </div>
    </div>

    <hr class="border-t border-gray-300 w-full mb-5" />
  </section>
</template>
