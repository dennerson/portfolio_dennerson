<template>
  <div class="projects">
    <h1 class="animated-text">Projects</h1>
    <div class="project-list">
      <ProjectCardVue
        v-for="project in projects"
        :key="project.id"
        :title="project.title"
        :description="project.description"
        :image="project.image"
        :demoLink="project.demoLink"
        :githubLink="project.githubLink"
      />
    </div>
  </div>
</template>

<script>
import ProjectCardVue from './ProjectCard.vue'

export default {
  components: {
    ProjectCardVue,
  },
  data() {
    return {
      projects: [
        {
          id: 1,
          title: 'Porfolio Website',
          description: 'A modern porfolio built with Vue.js and animations.',
          image: '../../img/portf.avif',
          demoLink: '#',
          githubLink: '#',
        },
        {
          id: 2,
          title: 'E-Commerce App',
          description: 'An online store with real-time product filtering.',
          image: '../../img/ecom.jpeg',
          demoLink: '#',
          githubLink: '#',
        },
        {
          id: 3,
          title: 'Task Manager',
          description: 'A simple task manager with drag-and-drop functionality.',
          image: '../../img/taskm.jpg',
          demoLink: '#',
          githubLink: '#',
        },
        {
          id: 4,
          title: 'Task Manager',
          description: 'A simple task manager with drag-and-drop functionality.',
          image: '../../img/taskm.jpg',
          demoLink: '#',
          githubLink: '#',
        },
        {
          id: 5,
          title: 'Task Manager',
          description: 'A simple task manager with drag-and-drop functionality.',
          image: '../../img/taskm.jpg',
          demoLink: '#',
          githubLink: '#',
        },
        {
          id: 6,
          title: 'Task Manager',
          description: 'A simple task manager with drag-and-drop functionality.',
          image: '../../img/taskm.jpg',
          demoLink: '#',
          githubLink: '#',
        },
      ],
    }
  },
}
</script>

<style scope>
.projects {
  /* display: flex; */
  gap: 20px;
  text-align: center;
  align-items: flex-start;
  flex-wrap: wrap;
  padding: 20px;
  max-width: 90%;
  margin: auto;
}
.project-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.project-card:hover {
  transform: scale(1.05);
  box-shadow: 0px 4px 15px #42b983;
}
.project-card img {
  width: 100%;
  border-radius: 8px;
  height: 200px;
  object-fit: cover;
}
.project-card a {
  display: inline-block;
  margin-top: 10px;
  padding: 8px;
  background: var(--vt-c-indigo);
  color: white;
  text-decoration: none;
  border-radius: 5px;
}
.project-card p {
  flex-grow: 1; /* Ensures text takes up space */
}
@media (prefers-color-scheme: dark) {
  .project-card:hover {
    box-shadow: 0px 4px 15px #42b983;
  }
}
</style>
