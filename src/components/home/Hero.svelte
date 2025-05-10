<script lang="ts">
  // 可以添加动画或其他交互逻辑
</script>

<section id="home" class="hero">
  <div class="hero-content">
    <h1 class="hero-title">创新科技 <span class="highlight">引领未来</span></h1>
    <p class="hero-subtitle">我们提供先进的技术解决方案，帮助企业实现数字化转型，提升竞争力</p>
    <div class="hero-buttons">
      <a href="#services" class="btn-primary">了解服务</a>
      <a href="#contact" class="btn-outline">联系我们</a>
    </div>
  </div>
  <div class="hero-image">
    <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="科技创新" />
  </div>
</section>

<style>
  .hero {
    display: flex;
    flex-direction: column-reverse;
    align-items: center;
    padding: 6rem 1rem 4rem;
    background-color: #f9fafb;
    overflow: hidden;
    min-height: 100vh;
  }
  
  .hero-content {
    max-width: 600px;
    text-align: center;
    margin-top: 2rem;
    z-index: 1;
  }
  
  .hero-title {
    font-size: 2.5rem;
    font-weight: 800;
    margin-bottom: 1.5rem;
    line-height: 1.2;
    color: #1f2937;
    font-family: 'Montserrat', sans-serif;
  }
  
  .highlight {
    color: #3b82f6;
    position: relative;
    display: inline-block;
  }
  
  .highlight::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 8px;
    background-color: rgba(59, 130, 246, 0.2);
    z-index: -1;
  }
  
  .hero-subtitle {
    font-size: 1.125rem;
    color: #4b5563;
    margin-bottom: 2rem;
    line-height: 1.6;
  }
  
  .hero-buttons {
    display: flex;
    gap: 1rem;
    justify-content: center;
    margin-bottom: 2rem;
  }
  
  .hero-image {
    width: 100%;
    max-width: 600px;
    margin-bottom: 2rem;
    border-radius: 1rem;
    overflow: hidden;
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
  }
  
  .hero-image img {
    width: 100%;
    height: auto;
    display: block;
  }
  
  @media (min-width: 1024px) {
    .hero {
      flex-direction: row;
      justify-content: space-between;
      padding: 0 4rem;
    }
    
    .hero-content {
      text-align: left;
      margin-top: 0;
      padding-right: 2rem;
    }
    
    .hero-title {
      font-size: 3.5rem;
    }
    
    .hero-buttons {
      justify-content: flex-start;
    }
    
    .hero-image {
      margin-bottom: 0;
      max-width: 50%;
    }
  }
</style>
