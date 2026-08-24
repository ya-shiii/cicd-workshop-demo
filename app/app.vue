<script setup lang="ts">
// SEO Meta Tags
useHead({
  title: 'CI/CD Workshop - Deployment Demo',
  meta: [
    { name: 'description', content: 'Demo page showing successful automated deployment for the CI/CD Workshop.' }
  ],
  link: [
    { rel: 'preconnect', href: 'https://fonts.googleapis.com' },
    { rel: 'preconnect', href: 'https://fonts.gstatic.com', crossorigin: '' },
    { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css2?family=Outfit:wght@400;600;800&display=swap' }
  ]
})
</script>

<template>
  <div class="demo-container">
    <NuxtRouteAnnouncer />
    
    <main class="card">
      <div class="header-section">
        <div class="badge">
          <span class="pulse-dot"></span>
          Live Demo
        </div>
        <h1 class="title">CI/CD Workshop</h1>
      </div>
      
      <div class="status-box">
        <p class="status-label">Deployment Status</p>
        <p class="status-version">Version 1.5</p>
      </div>

      <div class="footer-section">
        <p class="success-message">
          If you're reading this, deployment worked.
        </p>
      </div>
    </main>
  </div>
</template>
    
<style>
/* Global Reset and Styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: radial-gradient(circle at top, #1e293b, #0f172a);
  min-height: 100vh;
  color: #f8fafc;
  font-family: 'Outfit', system-ui, -apple-system, sans-serif;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

/* Page Container */
.demo-container {
  min-height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1.5rem;
  background: radial-gradient(circle at 50% 30%, rgba(56, 189, 248, 0.08), transparent 60%),
              radial-gradient(circle at 80% 80%, rgba(129, 140, 248, 0.06), transparent 50%);
}

/* Glassmorphic Card */
.card {
  background: rgba(30, 41, 59, 0.7);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 28px;
  padding: 3rem 2.5rem;
  width: 100%;
  max-width: 480px;
  text-align: center;
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5),
              0 0 40px rgba(56, 189, 248, 0.1);
  transform: translateY(20px);
  opacity: 0;
  animation: slideUp 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  transition: transform 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-4px);
  border-color: rgba(56, 189, 248, 0.25);
  box-shadow: 0 30px 60px -15px rgba(0, 0, 0, 0.6),
              0 0 50px rgba(56, 189, 248, 0.15);
}

/* Badges */
.badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(16, 185, 129, 0.1);
  border: 1px solid rgba(16, 185, 129, 0.2);
  color: #34d399;
  padding: 6px 14px;
  border-radius: 9999px;
  font-size: 0.875rem;
  font-weight: 600;
  margin-bottom: 1.5rem;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}

/* Pulsing Dot animation */
.pulse-dot {
  width: 8px;
  height: 8px;
  background-color: #10b981;
  border-radius: 50%;
  box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.7);
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0% {
    transform: scale(0.95);
    box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.7);
  }
  70% {
    transform: scale(1);
    box-shadow: 0 0 0 8px rgba(16, 185, 129, 0);
  }
  100% {
    transform: scale(0.95);
    box-shadow: 0 0 0 0 rgba(16, 185, 129, 0);
  }
}

/* Typography */
.title {
  font-size: 2.75rem;
  font-weight: 800;
  background: linear-gradient(135deg, #38bdf8 0%, #818cf8 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 2rem;
  letter-spacing: -0.03em;
}

.status-box {
  background: rgba(15, 23, 42, 0.5);
  border: 1px solid rgba(255, 255, 255, 0.05);
  border-radius: 18px;
  padding: 1.5rem;
  margin-bottom: 2rem;
}

.status-label {
  font-size: 0.95rem;
  color: #94a3b8;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 0.5rem;
  font-weight: 600;
}

.status-version {
  font-size: 1.75rem;
  font-weight: 800;
  color: #f1f5f9;
}

.success-message {
  font-size: 1.1rem;
  color: #cbd5e1;
  line-height: 1.6;
}

/* Entry Animation */
@keyframes slideUp {
  to {
    transform: translateY(0);
    opacity: 1;
  }
}
</style>
