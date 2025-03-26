<template>
  <div class="project-card">
    <img :src="image" :alt="title" class="project-image" />
    <div class="project-details">
      <h3 class="animated-text">{{ title }}</h3>
      <p class="animated-text">{{ description }}</p>
      <div class="links">
        <a :href="demoLink" target="_blank">Live Demo</a>
        <a :href="githubLink" target="_blank">GitHub</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    description: String,
    image: String,
    demoLink: String,
    githubLink: String,
  },
}
</script>

<style scoped>
.project-card {
  flex: 1 1 300px;
  flex-direction: column;
  border-radius: 8px;
  width: 100%;
  max-width: 350px;

  object-fit: cover;
  overflow: hidden;
  background: var(--color-background-soft);
  padding: 15px;
  text-align: center;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out;
}

.project-card:hover {
  transform: scale(1.05);
}

.project-image {
  border-radius: 8px;
}

.project-details {
  padding: 10px 0;
  color: white;
}

.links a {
  margin: 5px;
  color: var(--color-heading);
  text-decoration: none;
  font-weight: bold;
}

.links a:hover {
  text-decoration: underline;
}
</style>
