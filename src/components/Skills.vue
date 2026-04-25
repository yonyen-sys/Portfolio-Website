<template>
  <section class="section skills" id="skills">
    <div class="section-header">
      <span>Skills</span>
      <h2>Technical Expertise</h2>
    </div>
    <div class="skill-grid">
      <div v-for="skill in skills" :key="skill.name" class="skill-card">
        <div class="skill-icon">{{ skill.icon }}</div>
        <div>
          <h3>{{ skill.name }}</h3>
          <p>{{ skill.level }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      skills: [
        { name: 'Teaching JavaScript', level: 'Fundamentals, ES6, and modern web patterns', icon: '✨' },
        { name: 'Teaching PHP', level: 'Backend logic, Laravel, and CodeIgniter', icon: '🐘' },
        { name: 'Front-end Development', level: 'Vue.js, Nuxt.js, HTML, CSS, and responsive UI', icon: '💠' },
        { name: 'API Development', level: 'Laravel, NestJS, TypeORM, MySQL, and Postman', icon: '🔌' },
        { name: 'Project Delivery', level: 'Course design, management, and real project guidance', icon: '📁' },
        { name: 'Integration & Deployment', level: 'API integration, admin/POS systems, GitHub Pages', icon: '⚙️' }
      ]
    };
  }
};
</script>

<style scoped>
.skill-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(180px, 1fr));
  gap: 1rem;
}

.skill-card {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.2rem;
  border-radius: 22px;
  border: 1px solid rgba(37, 99, 235, 0.12);
  background: #f8fbff;
}

.skill-icon {
  width: 3rem;
  height: 3rem;
  display: grid;
  place-items: center;
  border-radius: 16px;
  background: rgba(37, 99, 235, 0.12);
  font-size: 1.25rem;
}

.skill-card h3 {
  margin: 0 0 0.35rem;
  font-size: 1.05rem;
}

.skill-card p {
  margin: 0;
  color: #475569;
  font-size: 0.97rem;
}

@media (max-width: 740px) {
  .skill-grid {
    grid-template-columns: 1fr;
  }
}
</style>
