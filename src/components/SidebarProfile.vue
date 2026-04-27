<script setup lang="ts">
const baseUrl = import.meta.env.BASE_URL

interface SocialLink {
  name: string
  url: string
}

const profile = {
  name: 'Werasak Mayer',
  email: 'werasak.mayer0@gmail.com',
  bio: 'I am a highly motivated computer engineering graduate and full-stack developer, ready to build scalable and efficient software solutions. With combined experience in developing end-to-end web applications, I have a strong foundation in both frontend and backend architectures, from designing responsive user interfaces to optimizing database schemas. My proficiency in modern tech stacks and system design empowers me to deliver high-performance applications and drive digital innovation.',
}

const socialLinks: SocialLink[] = [
  { name: 'Resume', url: `${baseUrl}werasak-mayer-resume.pdf` },
  { name: 'LinkedIn', url: 'https://www.linkedin.com/in/werasak-mayer-3348a4287/' },
  { name: 'GitHub', url: 'https://github.com/weerr12' },
]
</script>

<template>
  <div class="flex justify-center pb-8">
    <div class="w-full max-w-71.25 flex flex-col gap-4 text-sm text-gray-600">
      <h1 class="text-[28px] font-bold text-center text-blue-600 leading-tight">
        {{ profile.name }}
      </h1>

      <div class="relative w-full aspect-square mx-auto max-w-70 text-sm">
        <div class="absolute inset-0 rounded-full border-[3px] border-dashed border-gray-400" />
        <div class="absolute inset-3 rounded-full overflow-hidden">
          <img
            :src="`${baseUrl}profile.png`"
            :alt="`${profile.name} profile photo`"
            class="w-full h-full object-cover"
          />
        </div>
      </div>

      <nav class="flex justify-center gap-1 text-blue-500">
        <template v-for="(link, index) in socialLinks" :key="link.name">
          <a
            :href="link.url"
            :target="link.url !== '#' ? '_blank' : undefined"
            :rel="link.url !== '#' ? 'noopener noreferrer' : undefined"
            class="hover:underline"
          >
            {{ link.name }}
          </a>
          <span v-if="index < socialLinks.length - 1" class="text-gray-400">|</span>
        </template>
      </nav>

      <p class="leading-relaxed text-justify hyphens-auto">
        {{ profile.bio }}
      </p>

      <a
        :href="`mailto:${profile.email}`"
        class="hover:underline text-blue-600 hover:text-blue-500 transition-colors"
      >
        Email - {{ profile.email }}
      </a>
    </div>
  </div>
</template>
