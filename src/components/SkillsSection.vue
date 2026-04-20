<script setup lang="ts">
interface SkillCategory {
  name: string
  skills: string[]
}

const skillCategories: SkillCategory[] = [
  {
    name: 'Programming Languages',
    skills: ['JavaScript', 'TypeScript', 'Python', 'SQL'],
  },
  {
    name: 'Frontend',
    skills: ['HTML5', 'CSS', 'React', 'Next.js', 'Vue.js', 'Nuxt', 'Tailwind CSS'],
  },
  {
    name: 'Backend',
    skills: ['Node.js (Express, NestJS)', 'Prisma ORM', 'Drizzle ORM', 'RESTful APIs'],
  },
  {
    name: 'Other',
    skills: ['PostgreSQL', 'MySQL', 'Docker', 'Git', 'Postman', 'DBeaver'],
  },
]
</script>

<template>
  <section id="skills">
    <h2 class="text-[28px] font-bold text-gray-800 mb-5">Skills</h2>
    <hr class="border-t border-gray-300 mb-5" />

    <ul class="list-disc list-outside pl-8 space-y-2 mb-5 text-sm text-gray-500">
      <li v-for="category in skillCategories" :key="category.name">
        <span class="font-bold text-gray-500">{{ category.name }}:</span>
        {{ category.skills.join(', ') }}
      </li>
    </ul>
    <hr class="border-t border-gray-300 mb-5" />
  </section>
</template>
