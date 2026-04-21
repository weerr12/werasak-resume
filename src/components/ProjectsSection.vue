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
    description:
      'A comprehensive full-stack ecosystem designed to modernize outdoor trekking through community-driven trail management and a safety-first "Check-in" protocol. The platform bridges the gap between adventurers and local infrastructure while ensuring sustainable tourism through decentralized safety monitoring.',
    features: [
      'Safety Monitoring: Integrated a QR-based protocol for trail check-ins, enabling park administrators to track hiker status and reducing administrative overhead by 50%.',
      'SOS Automation: Engineered a high-reliability safety surveillance system using Node.js Cron Jobs to monitor return times and trigger proactive emergency alerts.',
      'Service Marketplace: Architected a robust marketplace connecting hikers with verified local guides and drivers, featuring an availability scheduling system.',
      'Eco-Carpooling: Built a centralized trip management system to facilitate group travel, optimizing transportation logistics and reducing carbon footprints.',
    ],
    tools: ['Nuxt 3', 'NestJS', 'Prisma', 'PostgreSQL', 'Docker', 'Cloudinary', 'Node-Cron'],
    githubUrl: 'https://github.com/weerr12/261492-Dernpa-Project',
    demoUrl: 'https://www.youtube.com/watch?v=BNi7zDLqB6o',
  },
  {
    title: 'Dustwatch | Full-Stack Developer',
    description:
      'A high-performance environmental monitoring solution providing real-time air quality insights. By leveraging a reactive architecture to process high-frequency sensor streams, the system delivers actionable hyper-local PM2.5 monitoring and intelligent safety zone navigation.',
    features: [
      'Real-time Pipeline: Architected a low-latency dashboard integrating live hardware sensor data via MQTT and external APIs for hyper-local PM2.5 accuracy.',
      'Safe Zone Algorithm: Engineered a proprietary triangulation algorithm that processes continuous sensor streams to instantly identify nearest low-pollution zones.',
      'Geospatial Maps: Implemented a high-performance map interface using Leaflet and dynamic heatmaps for real-time spatial air quality tracking.',
      'Secure OAuth: Integrated Google OAuth 2.0 for secure user session management and personalized safety preference storage.',
    ],
    tools: ['React', 'Node.js', 'Express', 'Prisma', 'PostgreSQL', 'Leaflet', 'Framer Motion', 'Zustand'],
    githubUrl: 'https://github.com/Phurinon/Project_SE_T14',
  },
  {
    title: 'Art and Community | Frontend Developer',
    description:
      'A sophisticated creative digital marketplace fostering creative economies. The platform focuses on high-performance user interaction and localized fintech integration, enabling artists to monetize work through low-friction financial transactions and inventory integrity.',
    features: [
      'Digital Scarcity: Streamlined a custom e-commerce workflow for digital assets, implementing logic-based scarcity controls to maintain inventory integrity.',
      'Fintech Integration: Engineered a seamless payment infrastructure by integrating automated PromptPay QR generation, bypassing high-fee gateways.',
      'State Sync: Leveraged TanStack Query for sophisticated server-state management, ensuring real-time consistency for large digital art catalogs.',
      'Creative Analytics: Developed a comprehensive reporting suite using Chart.js to provide artists with detailed insights into sales performance and engagement.',
    ],
    tools: ['React', 'Vite', 'TypeScript', 'TanStack Query', 'Chart.js', 'PromptPay-QR', 'Tailwind CSS'],
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
              class="inline-flex items-center gap-1.5 p-1 rounded text-white text-[10px] font-medium bg-gray-800 hover:bg-gray-700 transition-colors"
            >
              <Github :size="14" /> View on GitHub
            </a>
            <a
              v-if="project.demoUrl"
              :href="project.demoUrl"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center gap-1.5 p-1 rounded text-white text-[10px] font-medium bg-red-600 hover:bg-red-500 transition-colors"
            >
              <Youtube :size="14" />
              View on YouTube
            </a>
          </div>

          <p class="text-sm text-gray-600 leading-relaxed text-justify mb-4 italic">
            "{{ project.description }}"
          </p>

          <ul class="list-disc list-outside pl-8 space-y-2 mb-5">
            <li v-for="feature in project.features" :key="feature" class="text-base text-gray-700">
              <span class="font-semibold text-gray-800 text-sm">{{ feature.split(':')[0] }}</span>
              <span v-if="feature.includes(':')" class="text-gray-600"
                >: {{ feature.split(':').slice(1).join(':') }}</span
              >
            </li>
          </ul>

          <div class="flex flex-wrap gap-2 mt-4">
            <span
              v-for="tool in project.tools"
              :key="tool"
              class="px-2 py-0.5 bg-blue-50 text-blue-700 text-[11px] font-medium rounded-full border border-blue-100"
            >
              {{ tool }}
            </span>
          </div>
        </div>

        <hr class="border-t border-gray-100 w-full mt-8" />
      </template>
    </div>
  </section>
</template>
