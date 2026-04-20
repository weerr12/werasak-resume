<script setup lang="ts">
import { Github, Youtube } from 'lucide-vue-next'

interface Project {
  title: string
  description: string
  features: string[]
  tools: string[]
  githubUrl: string
  demoUrl?: string
}

const projects: Project[] = [
  {
    title: 'Dernpa | Full-Stack Developer',
    description: 'Trekking Management and Safety Platform.',
    features: [
      'Implemented a real-time QR-based Check-in/Out system for hikers, reducing administrative processing time by 50% compared to traditional paper-based methods.',
      'Engineered an automated emergency alert system using Node.js Cron Jobs to monitor hiker safety status every 60 seconds, enabling proactive search and rescue responses.',
    ],
    tools: ['Nuxt', 'Tailwind CSS', 'NestJS', 'Prisma', 'PostgreSQL', 'Docker'],
    githubUrl: 'https://github.com/weerr12/261492-Dernpa-Project',
    demoUrl: 'https://www.youtube.com/watch?v=BNi7zDLqB6o',
  },
  {
    title: 'Dustwatch | Full-Stack Developer',
    description: 'Real-time Air Quality Monitoring and Safety Zone Finder.',
    features: [
      'Architected a real-time air quality dashboard by integrating live hardware sensor data via MQTT protocol and external APIs, delivering hyper-local PM2.5 accuracy for end-users.',
      'Engineered a Safe Zone algorithm that instantly triangulates the nearest low-pollution areas by processing continuous, high-frequency sensor streams, ensuring reliable safety guidance.',
    ],
    tools: ['React', 'Node.js', 'Socket.io', 'MongoDB', 'Redis'],
    githubUrl: 'https://github.com/Phurinon/Project_SE_T14',
  },
  {
    title: 'Art and Community | Frontend Developer',
    description: 'Digital Art Marketplace and Community Platform.',
    features: [
      'Streamlined a custom e-commerce workflow for digital artists, implementing automated scarcity control to maintain inventory integrity for limited-edition asset sales.',
      'Developed a localized payment infrastructure by integrating PromptPay QR generation, successfully bypassing high-fee gateways and maximizing transaction conversion rates in the Thai market.',
    ],
    tools: ['Next.js', 'TypeScript', 'Prisma', 'TailwindCSS', 'PostgreSQL'],
    githubUrl: 'https://github.com/SUPATKN/Art-and-Community',
  },
]
</script>

<template>
  <section id="projects">
    <h2 class="text-3xl font-bold text-gray-800 mb-5">Projects</h2>
    <hr class="border-t border-gray-300 w-full mb-5" />

    <div class="space-y-8 mb-5">
      <template v-for="project in projects" :key="project.title">
        <div>
          <h3 class="text-xl font-bold text-gray-800 mb-3">{{ project.title }}</h3>
          <div class="flex flex-wrap gap-2 mb-4">
            <a
              :href="project.githubUrl"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center gap-1.5 p-1 rounded text-white text-[10px] font-medium bg-gray-800 hover:bg-gray-700"
            >
              <Github :size="16" /> View on GitHub
            </a>
            <a
              v-if="project.demoUrl"
              :href="project.demoUrl"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center gap-1.5 p-1 rounded text-white text-[10px] font-medium bg-red-600 hover:bg-red-500"
            >
              <Youtube :size="16" />
              View on YouTube
            </a>
          </div>

          <p class="text-sm text-gray-500 leading-relaxed text-justify mb-4">
            {{ project.description }}
          </p>

          <ul class="list-disc list-outside pl-8 space-y-2 mb-4">
            <li v-for="feature in project.features" :key="feature" class="text-base text-gray-700">
              <span class="text-gray-500 text-sm">{{ feature.split(':')[0] }}</span>
              <span v-if="feature.includes(':')"
                >: {{ feature.split(':').slice(1).join(':') }}</span
              >
            </li>
          </ul>
        </div>

        <hr class="border-t border-gray-300 w-full" />
      </template>
    </div>
  </section>
</template>
