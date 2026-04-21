<script setup lang="ts">
import { Github, Youtube } from 'lucide-vue-next'

interface ToolCategory {
  category: string
  items: string[]
}

interface Project {
  title: string
  description: string
  features: string[]
  tools: ToolCategory[]
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
    tools: [
      { category: 'Platform', items: ['Docker', 'Docker Compose'] },
      { category: 'Backend', items: ['NestJS', 'Node.js'] },
      { category: 'Frontend', items: ['Nuxt 3', 'Vue.js', 'Tailwind CSS'] },
      { category: 'Database', items: ['PostgreSQL', 'Prisma ORM'] },
      { category: 'Authentication', items: ['Passport.js', 'JWT', 'Google OAuth'] },
      { category: 'Services', items: ['Cloudinary API (Media)', 'Node-Cron (Safety Monitoring)'] },
    ],
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
    tools: [
      { category: 'Platform', items: ['Docker', 'Docker Compose'] },
      { category: 'Backend', items: ['Node.js', 'Express.js'] },
      { category: 'Frontend', items: ['React.js', 'Vite', 'Framer Motion'] },
      { category: 'Database', items: ['PostgreSQL', 'Prisma ORM'] },
      { category: 'Maps & Geospatial', items: ['Leaflet', 'React-Leaflet'] },
      { category: 'State Management', items: ['Zustand'] },
      { category: 'Visualization', items: ['Recharts'] },
      { category: 'Security', items: ['Google OAuth 2.0'] },
    ],
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
    tools: [
      { category: 'Frontend Core', items: ['React.js', 'Vite', 'TypeScript'] },
      { category: 'State & Sync', items: ['TanStack Query (React Query)', 'Axios'] },
      { category: 'Fintech Integration', items: ['PromptPay-QR', 'QRCode.js'] },
      { category: 'Visualization', items: ['Chart.js', 'React-Chartjs-2'] },
      { category: 'UI Frameworks', items: ['Tailwind CSS', 'Bootstrap', 'React-Bootstrap'] },
      { category: 'Icons', items: ['Lucide Icons', 'FontAwesome'] },
    ],
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
        <div class="group">
          <h3 class="text-2xl font-bold text-gray-800 mb-3">{{ project.title }}</h3>
          <div class="flex flex-wrap gap-2 mb-4">
            <a
              :href="project.githubUrl"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center gap-1.5 p-1 px-2 rounded text-white text-[11px] font-medium bg-gray-800 hover:bg-gray-700 transition-colors"
            >
              <Github :size="14" /> View on GitHub
            </a>
            <a
              v-if="project.demoUrl"
              :href="project.demoUrl"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center gap-1.5 p-1 px-2 rounded text-white text-[11px] font-medium bg-red-600 hover:bg-red-500 transition-colors"
            >
              <Youtube :size="14" />
              View on YouTube
            </a>
          </div>

          <p class="text-sm text-gray-600 leading-relaxed text-justify mb-6 italic">
            "{{ project.description }}"
          </p>

          <div>
            <h4 class="text-lg font-bold text-gray-800 mb-3 flex items-center gap-2">
              <span class="w-1.5 h-6 bg-blue-600 rounded-full"></span>
              Key Features
            </h4>
            <ul class="list-disc list-outside pl-8 space-y-2 mb-8">
              <li
                v-for="feature in project.features"
                :key="feature"
                class="text-base text-gray-700 group/item"
              >
                <span
                  class="font-semibold text-gray-800 text-sm group-hover/item:text-blue-700 transition-colors"
                >
                  {{ feature.split(':')[0] }}
                </span>
                <span v-if="feature.includes(':')" class="text-gray-600"
                  >: {{ feature.split(':').slice(1).join(':') }}</span
                >
              </li>
            </ul>
          </div>

          <div>
            <h4 class="text-lg font-bold text-gray-800 mb-3 flex items-center gap-2">
              <span class="w-1.5 h-6 bg-gray-400 rounded-full"></span>
              Tools / Technologies
            </h4>
            <div class="grid grid-cols-1 gap-x-8 gap-y-2 pl-4">
              <div
                v-for="group in project.tools"
                :key="group.category"
                class="text-sm border-l-2 border-gray-100 pl-3"
              >
                <span class="font-bold text-gray-700 block md:inline">{{ group.category }}:</span>
                <span class="text-gray-600 md:ml-1">{{ group.items.join(', ') }}</span>
              </div>
            </div>
          </div>
        </div>

        <hr class="border-t border-gray-200 w-full mt-10" />
      </template>
    </div>
  </section>
</template>
