<script lang="ts">
  // 服务数据
  const services = [
    {
      icon: '💻',
      title: '网站开发',
      description: '我们提供专业的网站设计与开发服务，打造响应式、高性能的现代化网站，提升您的在线形象。'
    },
    {
      icon: '📱',
      title: '移动应用',
      description: '开发跨平台移动应用，为iOS和Android用户提供流畅的用户体验，帮助企业拓展移动市场。'
    },
    {
      icon: '🔄',
      title: '数字化转型',
      description: '通过数字化工具和流程优化，帮助传统企业实现业务转型，提高运营效率和市场竞争力。'
    },
    {
      icon: '🛡️',
      title: '网络安全',
      description: '提供全面的网络安全解决方案，保护您的业务数据和客户信息，防范各类网络威胁。'
    },
    {
      icon: '📊',
      title: '数据分析',
      description: '利用先进的数据分析技术，挖掘业务数据价值，为企业决策提供数据支持和洞察。'
    },
    {
      icon: '☁️',
      title: '云服务',
      description: '提供可靠的云计算服务，包括云存储、服务器托管和云应用开发，满足企业灵活扩展需求。'
    }
  ];
</script>

<section id="services" class="section">
  <h2 class="section-title">我们的服务</h2>
  <p class="section-subtitle">提供全方位的技术解决方案，满足您的业务需求</p>
  
  <div class="services-grid">
    {#each services as service}
      <div class="service-card">
        <div class="service-icon">{service.icon}</div>
        <h3 class="service-title">{service.title}</h3>
        <p class="service-description">{service.description}</p>
        <a href="#contact" class="service-link">了解更多</a>
      </div>
    {/each}
  </div>
</section>

<style>
  .services-grid {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 2rem;
  }
  
  .service-card {
    background-color: white;
    border-radius: 0.5rem;
    padding: 2rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  
  .service-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
  }
  
  .service-icon {
    font-size: 2.5rem;
    margin-bottom: 1.5rem;
  }
  
  .service-title {
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 1rem;
    color: #1f2937;
  }
  
  .service-description {
    color: #4b5563;
    margin-bottom: 1.5rem;
    line-height: 1.6;
  }
  
  .service-link {
    color: #3b82f6;
    font-weight: 500;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    transition: color 0.3s;
  }
  
  .service-link:hover {
    color: #2563eb;
  }
  
  .service-link::after {
    content: '→';
    margin-left: 0.5rem;
    transition: transform 0.3s;
  }
  
  .service-link:hover::after {
    transform: translateX(4px);
  }
  
  @media (min-width: 640px) {
    .services-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  
  @media (min-width: 1024px) {
    .services-grid {
      grid-template-columns: repeat(3, 1fr);
    }
  }
</style>
