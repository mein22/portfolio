<template>
  <section class="py-24">
    <div class="max-w-7xl mx-auto px-6">

      <!-- Section header -->
      <div class="text-center mb-16">
        <p class="text-sm text-gray-200 uppercase tracking-widest">
          What Skills I Have
        </p>
        <h2 class="text-4xl font-bold text-[#cb6ce6] mt-2">
          My Experience
        </h2>
      </div>

      <!-- Skill Cards -->
      <div class="grid gap-10 lg:grid-cols-2">

        <!-- Frontend -->
        <div class="relative rounded-2xl p-8 bg-[#151a33]">

          <!-- Glow border -->
          <div class="absolute inset-0 rounded-2xl border border-transparent
                      bg-gradient-to-r from-blue-500 to-purple-500 opacity-20"></div>

          <h3 class="text-xl font-semibold text-white mb-8 relative">
            Frontend Development
          </h3>

          <div class="grid grid-cols-2 gap-y-6 relative">
            <div
              v-for="skill in frontendSkills"
              :key="skill.name"
              class="flex items-start gap-3"
            >
              <span class="text-blue-400 mt-1">✔</span>
              <div>
                <p class="text-white font-medium">
                  {{ skill.name }}
                </p>
                <p class="text-sm text-gray-400">
                  {{ skill.level }}
                </p>
              </div>
            </div>
          </div>
        </div>

        <!-- Backend -->
        <div class="relative rounded-2xl p-8 bg-[#151a33]">

          <div class="absolute inset-0 rounded-2xl border border-transparent
                      bg-gradient-to-r from-blue-500 to-purple-500 opacity-20"></div>

          <h3 class="text-xl font-semibold text-white mb-8 relative">
            Backend Development
          </h3>

          <div class="grid grid-cols-2 gap-y-6 relative">
            <div
              v-for="skill in backendSkills"
              :key="skill.name"
              class="flex items-start gap-3"
            >
              <span class="text-blue-400 mt-1">✔</span>
              <div>
                <p class="text-white font-medium">
                  {{ skill.name }}
                </p>
                <p class="text-sm text-gray-400">
                  {{ skill.level }}
                </p>
              </div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "SkillsSection",
  data() {
    return {
      frontendSkills: [
        { name: "HTML", level: "Experienced" },
        { name: "CSS", level: "Experienced" },
        { name: "JavaScript", level: "Experienced" },
        { name: "TypeScript", level: "Experienced" },
        { name: "Bootstrap", level: "Experienced" },
        { name: "Tailwind", level: "Experienced" },
        { name: "Vue", level: "Experienced" },
        { name: "React", level: "Experienced" },
      ],
      backendSkills: [
        { name: "Phyton", level: "Intermediate" },
        { name: "Node.js", level: "Intermediate" },
        { name: "Flask", level: "Intermediate" },
        { name: "Express.js", level: "Intermediate" },
        { name: "SQL", level: "Intermediate" },
      ],
    };
  },
};
</script>
