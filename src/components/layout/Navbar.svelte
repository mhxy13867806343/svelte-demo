<script lang="ts">
  let isMenuOpen = $state(false);
  
  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
  
  // 导航链接
  const navLinks = [
    { text: '首页', href: '#home' },
    { text: '关于我们', href: '#about' },
    { text: '服务', href: '#services' },
    { text: '案例', href: '#portfolio' },
    { text: '联系我们', href: '#contact' }
  ];
</script>

<header class="navbar">
  <div class="navbar-container">
    <div class="logo">
      <a href="#home">
        <span class="company-name">科技企业</span>
      </a>
    </div>
    
    <button class="mobile-menu-button" on:click={toggleMenu} aria-label="菜单">
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </button>
    
    <nav class="nav-links" class:active={isMenuOpen}>
      <ul>
        {#each navLinks as link}
          <li>
            <a href={link.href} on:click={() => isMenuOpen = false}>{link.text}</a>
          </li>
        {/each}
      </ul>
      <div class="nav-cta">
        <a href="#contact" class="btn-primary">联系我们</a>
      </div>
    </nav>
  </div>
</header>

<style>
  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: rgba(255, 255, 255, 0.95);
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    z-index: 1000;
  }
  
  .navbar-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    max-width: 1200px;
    margin: 0 auto;
  }
  
  .logo {
    display: flex;
    align-items: center;
  }
  
  .company-name {
    font-size: 1.5rem;
    font-weight: 700;
    color: #3b82f6;
    font-family: 'Montserrat', sans-serif;
  }
  
  .nav-links {
    display: flex;
    align-items: center;
  }
  
  .nav-links ul {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  .nav-links li {
    margin: 0 1rem;
  }
  
  .nav-links a {
    color: #1f2937;
    text-decoration: none;
    font-weight: 500;
    transition: color 0.3s;
    padding: 0.5rem 0;
    position: relative;
  }
  
  .nav-links a:hover {
    color: #3b82f6;
  }
  
  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background-color: #3b82f6;
    transition: width 0.3s;
  }
  
  .nav-links a:hover::after {
    width: 100%;
  }
  
  .nav-cta {
    margin-left: 2rem;
  }
  
  .mobile-menu-button {
    display: none;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
  }
  
  .bar {
    display: block;
    width: 25px;
    height: 3px;
    margin: 5px auto;
    background-color: #1f2937;
    transition: all 0.3s;
  }
  
  @media (max-width: 768px) {
    .mobile-menu-button {
      display: block;
    }
    
    .nav-links {
      position: fixed;
      top: 70px;
      left: -100%;
      width: 100%;
      height: calc(100vh - 70px);
      background-color: white;
      flex-direction: column;
      padding: 2rem;
      transition: left 0.3s ease;
    }
    
    .nav-links.active {
      left: 0;
    }
    
    .nav-links ul {
      flex-direction: column;
      width: 100%;
    }
    
    .nav-links li {
      margin: 1rem 0;
      width: 100%;
      text-align: center;
    }
    
    .nav-cta {
      margin: 2rem 0 0 0;
    }
  }
</style>
