<script setup lang="ts">
import SidebarProfile from '@/components/SidebarProfile.vue'
import SkillsSection from '@/components/SkillsSection.vue'
import ExperienceSection from '@/components/ExperienceSection.vue'
import ProjectsSection from '@/components/ProjectsSection.vue'
import EducationSection from '@/components/EducationSection.vue'
import CustomParticles from '@/components/CustomParticles.vue'

const currentYear = new Date().getFullYear()
</script>

<template>
  <div class="relative min-h-screen p-6 lg:p-12">
    <CustomParticles />

    <div class="relative z-10 max-w-7xl mx-auto">
      <div class="lg:grid lg:grid-cols-[650px_1fr]">
        <aside class="relative">
          <div class="lg:fixed lg:top-12 lg:w-[650px]">
            <SidebarProfile />
          </div>
        </aside>

        <main class="w-full min-w-0 flex flex-col">
          <SkillsSection />
          <ExperienceSection />
          <ProjectsSection />
          <EducationSection />
          <footer class="text-left py-8 text-sm text-gray-400">
            <p>© {{ currentYear }} Werasak Mayer. Powered by Vue.js</p>
          </footer>
        </main>
      </div>
    </div>
  </div>
</template>
