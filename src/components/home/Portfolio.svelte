<script lang="ts">
  // 案例数据
  const portfolioItems = [
    {
      title: '智慧城市管理平台',
      category: '政府项目',
      image: 'https://images.unsplash.com/photo-1477959858617-67f85cf4f1df?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80',
      description: '为某省会城市打造的智慧城市管理平台，整合城市资源，提升城市管理效率，实现数据可视化监控。'
    },
    {
      title: '电商平台重构',
      category: '零售行业',
      image: 'https://images.unsplash.com/photo-1607082348824-0a96f2a4b9da?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80',
      description: '帮助某知名电商平台进行技术架构重构，提升系统性能和用户体验，支持千万级用户访问。'
    },
    {
      title: '医疗健康管理系统',
      category: '医疗行业',
      image: 'https://images.unsplash.com/photo-1576091160550-2173dba999ef?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80',
      description: '为三甲医院开发的患者健康管理系统，整合医疗资源，提供在线问诊、健康档案管理等功能。'
    },
    {
      title: '金融风控系统',
      category: '金融行业',
      image: 'https://images.unsplash.com/photo-1563986768609-322da13575f3?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80',
      description: '为某银行开发的智能风控系统，利用AI技术识别潜在风险，提高贷款审批效率和准确率。'
    },
    {
      title: '工业物联网平台',
      category: '制造业',
      image: 'https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80',
      description: '为制造企业打造的工业物联网平台，实现设备远程监控、预测性维护，提升生产效率。'
    },
    {
      title: '教育在线学习平台',
      category: '教育行业',
      image: 'https://images.unsplash.com/photo-1501504905252-473c47e087f8?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80',
      description: '为教育机构开发的在线学习平台，提供直播课堂、课程管理、学习进度跟踪等功能。'
    }
  ];
  
  // 过滤分类
  const categories = ['全部', ...new Set(portfolioItems.map(item => item.category))];
  let activeCategory = $state('全部');
  
  // 过滤后的项目
  const filteredItems = $derived(activeCategory === '全部' 
    ? portfolioItems 
    : portfolioItems.filter(item => item.category === activeCategory));
  
  // 设置活动分类
  function setCategory(category) {
    activeCategory = category;
  }
</script>

<section id="portfolio" class="section">
  <h2 class="section-title">成功案例</h2>
  <p class="section-subtitle">我们为各行业客户提供的成功解决方案</p>
  
  <div class="portfolio-filter">
    {#each categories as category}
      <button 
        class="filter-button" 
        class:active={activeCategory === category}
        on:click={() => setCategory(category)}
      >
        {category}
      </button>
    {/each}
  </div>
  
  <div class="portfolio-grid">
    {#each filteredItems as item}
      <div class="portfolio-item">
        <div class="portfolio-image">
          <img src={item.image} alt={item.title} />
          <div class="portfolio-overlay">
            <span class="portfolio-category">{item.category}</span>
            <h3 class="portfolio-title">{item.title}</h3>
            <p class="portfolio-description">{item.description}</p>
            <a href="#contact" class="portfolio-link">了解详情</a>
          </div>
        </div>
      </div>
    {/each}
  </div>
</section>

<style>
  .portfolio-filter {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 0.75rem;
    margin-bottom: 2.5rem;
  }
  
  .filter-button {
    background-color: transparent;
    border: 1px solid #e5e7eb;
    color: #4b5563;
    padding: 0.5rem 1rem;
    border-radius: 9999px;
    font-size: 0.875rem;
    cursor: pointer;
    transition: all 0.3s;
  }
  
  .filter-button:hover {
    background-color: #f3f4f6;
  }
  
  .filter-button.active {
    background-color: #3b82f6;
    border-color: #3b82f6;
    color: white;
  }
  
  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 2rem;
  }
  
  .portfolio-item {
    border-radius: 0.5rem;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    position: relative;
  }
  
  .portfolio-image {
    position: relative;
    overflow: hidden;
    height: 300px;
  }
  
  .portfolio-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.5s;
  }
  
  .portfolio-item:hover .portfolio-image img {
    transform: scale(1.1);
  }
  
  .portfolio-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    padding: 1.5rem;
    background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
    color: white;
    transform: translateY(100px);
    transition: transform 0.3s;
  }
  
  .portfolio-item:hover .portfolio-overlay {
    transform: translateY(0);
  }
  
  .portfolio-category {
    display: inline-block;
    background-color: #3b82f6;
    color: white;
    padding: 0.25rem 0.75rem;
    border-radius: 9999px;
    font-size: 0.75rem;
    margin-bottom: 0.75rem;
  }
  
  .portfolio-title {
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 0.5rem;
  }
  
  .portfolio-description {
    font-size: 0.875rem;
    margin-bottom: 1rem;
    opacity: 0.9;
  }
  
  .portfolio-link {
    color: #3b82f6;
    font-weight: 500;
    text-decoration: none;
    font-size: 0.875rem;
    display: inline-flex;
    align-items: center;
    transition: color 0.3s;
  }
  
  .portfolio-link:hover {
    color: #60a5fa;
  }
  
  .portfolio-link::after {
    content: '→';
    margin-left: 0.25rem;
    transition: transform 0.3s;
  }
  
  .portfolio-link:hover::after {
    transform: translateX(4px);
  }
  
  @media (min-width: 640px) {
    .portfolio-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  
  @media (min-width: 1024px) {
    .portfolio-grid {
      grid-template-columns: repeat(3, 1fr);
    }
  }
</style>
