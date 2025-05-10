<script lang="ts">
  // 导入布局组件
  import Navbar from './components/layout/Navbar.svelte';
  import Footer from './components/layout/Footer.svelte';
  
  // 导入页面组件
  import Hero from './components/home/Hero.svelte';
  import Services from './components/home/Services.svelte';
  import About from './components/home/About.svelte';
  import Portfolio from './components/home/Portfolio.svelte';
  import Contact from './components/home/Contact.svelte';
</script>

<div class="app">
  <Navbar />
  
  <main class="main-content">
    <Hero />
    <Services />
    <About />
    <Portfolio />
    <Contact />
  </main>
  
  <Footer />
</div>

<style>
  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }
  
  .main-content {
    flex: 1;
    padding-top: 70px; /* 为固定导航栏留出空间 */
  }
</style>
