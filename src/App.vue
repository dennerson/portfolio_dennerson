<template>
  <div :class="{ dark: isDarkMode }">
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/certificates">Certifications</router-link>
      <router-link to="/contact">Contact</router-link>

      <button @click="toogleDarkMode">
        {{ isDarkMode ? '☀️ Light Mode' : '🌙 Dark Mode' }}
      </button>
    </nav>

    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" />
      </transition>
    </router-view>
  </div>
</template>

<script scoped>
export default {
  data() {
    return {
      isDarkMode: localStorage.getItem('darkMode') === 'true',
    }
  },
  watch: {
    isDarkMode(newVal) {
      if (newVal) {
        document.body.classList.add('dark')
      } else {
        document.body.classList.remove('dark')
      }
      localStorage.setItem('darkMode', newVal)
    },
  },
  mounted() {
    if (this.isDarkMode) {
      document.body.classList.add('dark')
    }
  },
  methods: {
    toogleDarkMode() {
      this.isDarkMode = !this.isDarkMode
      localStorage.setItem('darkMode', this.isDarkMode)
    },
  },
}
</script>

<style>
/* Default Light Mode */
body {
  background-color: #f8f9fa;
  color: #333;

  min-height: 100vh;
  background: url('../../img/work-set-up2.jpg') no-repeat;
  background-size: cover;
  background-position: center center;
  background-attachment: fixed;
  filter: blur(0px);
  justify-content: center;
  align-content: center;
  /* display: flex; */
  flex-direction: column;

  transition:
    background 0.3s ease,
    color 0.3s ease;
}
/* DarkMode Styles */
body.dark {
  background-color: #1e1e1e;
  color: #ddd;

  min-height: 100vh;
  background: url('../../img/work-set-up.jpg') no-repeat;
  background-size: cover;
  background-position: center center;
  background-attachment: fixed;
  filter: blur(0px);
  justify-content: center;
  align-content: center;
  /* display: flex; */
  flex-direction: column;
}
nav {
  display: flex;
  gap: 15px;
  padding: 5px;
  background-color: rgba(34, 34, 34, 0.9);
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
}
nav a {
  color: white;
  text-decoration: none;
  transition: 0.3s ease-in-out;
}
nav a:hover {
  color: #42b983;
}
/* Page transition animations */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
button {
  margin-left: auto;
  background: none;
  border: none;
  color: white;
  cursor: pointer;
  transition: color 0.3s ease-in-out;
}
button:hover {
  color: #42b983;
}

#app {
  padding-top: 50px; /* Adjust this to match the navbar height */
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
.animated-text {
  animation: fadeInUp 0.8s ease-in-out;
}

.app-container {
  min-height: 100vh;
  background: url('../../img/work-set-up2.jpg') no-repeat;
  background-size: cover;
  background-position: center center;
  background-attachment: fixed;
  filter: blur(0px);
  image-rendering: crisp-edges;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

/* .dark {
  min-height: 100vh;
  background: url('../../img/work-set-up2.jpg');
  background-size: cover;
  display: flex;
  flex-direction: column;
} */

.home-section {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 50px;
}

.welcome-text {
  background: rgba(0, 0, 0, 0.5);
  padding: 15px;
  border-radius: 5px;
  color: white;
}
</style>
