<template>
  <section class="section contact" id="contact">
    <div class="section-header">
      <span>Contact</span>
      <h2>Let’s talk</h2>
    </div>
    <div class="contact-grid">
      <div class="contact-card">
        <h3>Email</h3>
        <a href="mailto:yon.yen@passerellesnumeriques.org">yon.yen@passerellesnumeriques.org</a>
      </div>
      <div class="contact-card">
        <h3>GitHub</h3>
        <a href="https://github.com/yonyen-sys" target="_blank" rel="noreferrer">github.com/yonyen-sys</a>
      </div>
      <div class="contact-card">
        <h3>Phone</h3>
        <a href="tel:086750534">086750534</a>
      </div>
      <div class="contact-card">
        <h3>Location</h3>
        <p>#54, St. 271, Phom Trapeang, Chhuk Bory Sola, Sangkat Teok Thla, Khan Sen Sok, Phnom Penh, Cambodia</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact'
};
</script>

<style scoped>
.contact-grid {
  display: grid;
  grid-template-columns: repeat(4, minmax(200px, 1fr));
  gap: 1rem;
}

.contact-card {
  padding: 1.5rem;
  border-radius: 24px;
  background: #f8fafc;
  border: 1px solid rgba(37, 99, 235, 0.12);
}

.contact-card h3 {
  margin: 0 0 0.9rem;
  font-size: 1.05rem;
}

.contact-card a {
  color: var(--text);
  text-decoration: none;
  word-break: break-all;
}

.contact-card a:hover {
  color: var(--primary);
}

@media (max-width: 900px) {
  .contact-grid {
    grid-template-columns: 1fr;
  }
}
</style>
