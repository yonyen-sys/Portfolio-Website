<template>
  <section class="section projects" id="projects">
    <div class="section-header">
      <span>Work</span>
      <h2>Selected Projects</h2>
    </div>
    <div class="project-grid">
      <article v-for="project in projects" :key="project.title" class="project-card">
        <div class="project-top">
          <span class="project-tag">{{ project.role }}</span>
          <a class="project-link" :href="project.url" target="_blank" rel="noreferrer">View live</a>
        </div>
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <div class="project-stack">
          <span v-for="item in project.stack" :key="item">{{ item }}</span>
        </div>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Projects',
  data() {
    return {
      projects: [
        {
          title: 'Alumini Media',
          description: 'A responsive login experience for an alumni media platform with clean UI and accessible form flows.',
          stack: ['Vue', 'CSS', 'Responsive Design'],
          url: 'https://tolakh.site/login'
        },
        {
          title: 'អាណាចក្រភំ្នស្វាយ',
          description: 'A Khmer-language web app with vibrant visuals and a modern front-end experience.',
          stack: ['Vue', 'Vercel', 'UI Design'],
          url: 'https://finall-vc1.vercel.app/'
        },
        {
          title: 'CHONG CHOUL',
          description: 'A live website for a local business with polished navigation, content layout, and responsive presentation.',
          stack: ['Vue', 'Responsive Layout', 'SEO Friendly'],
          url: 'https://chongchoul.online/?authuser=0'
        },
        {
          title: 'គម្ពី-ELibrary',
          description: 'An e-library application with book discovery and readable content built for modern browsers.',
          stack: ['Vue', 'PWA', 'Accessibility'],
          url: 'https://e-library.app/'
        }
      ]
    };
  }
};
</script>

<style scoped>
.project-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(260px, 1fr));
  gap: 1rem;
}

.project-card {
  padding: 1.5rem;
  border-radius: 24px;
  border: 1px solid rgba(15, 23, 42, 0.08);
  background: #ffffff;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.project-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}

.project-tag {
  display: inline-flex;
  padding: 0.45rem 0.8rem;
  border-radius: 999px;
  background: rgba(37, 99, 235, 0.12);
  color: #1d4ed8;
  font-size: 0.85rem;
  font-weight: 700;
}

.project-link {
  color: var(--primary);
  text-decoration: none;
  font-weight: 600;
}

.project-card h3 {
  margin: 0;
  font-size: 1.2rem;
}

.project-card p {
  margin: 0;
  color: var(--muted);
  line-height: 1.8;
}

.project-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.project-stack span {
  padding: 0.5rem 0.75rem;
  border-radius: 999px;
  background: #f8fafc;
  border: 1px solid rgba(15, 23, 42, 0.08);
  font-size: 0.9rem;
}

@media (max-width: 900px) {
  .project-grid {
    grid-template-columns: 1fr;
  }
}
</style>
