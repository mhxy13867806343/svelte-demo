<script lang="ts">
  // 公司统计数据
  const stats = [
    { value: '10+', label: '年行业经验' },
    { value: '200+', label: '成功案例' },
    { value: '50+', label: '专业团队' },
    { value: '98%', label: '客户满意度' }
  ];
  
  // 团队成员
  const teamMembers = [
    {
      name: '张明',
      position: '创始人 & CEO',
      image: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80',
      description: '拥有15年互联网行业经验，曾任多家知名科技公司高管，致力于推动企业数字化转型。'
    },
    {
      name: '李婷',
      position: '技术总监',
      image: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80',
      description: '计算机科学博士，专注于人工智能和大数据技术研究，带领团队开发多项创新技术解决方案。'
    },
    {
      name: '王强',
      position: '产品经理',
      image: 'https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80',
      description: '拥有丰富的产品设计和用户体验经验，专注于打造简洁易用、功能强大的产品。'
    }
  ];
</script>

<section id="about" class="section">
  <div class="about-container">
    <div class="about-content">
      <h2 class="section-title">关于我们</h2>
      <p class="about-description">
        我们是一家专注于提供创新技术解决方案的企业，成立于2015年，致力于帮助各行业客户实现数字化转型，提升业务效率和市场竞争力。
      </p>
      <p class="about-description">
        凭借专业的技术团队和丰富的行业经验，我们为客户提供从咨询规划到实施落地的全流程服务，确保每个项目都能达到预期目标，创造实际价值。
      </p>
      
      <div class="stats-container">
        {#each stats as stat}
          <div class="stat-item">
            <div class="stat-value">{stat.value}</div>
            <div class="stat-label">{stat.label}</div>
          </div>
        {/each}
      </div>
    </div>
    
    <div class="about-image">
      <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="我们的团队" />
    </div>
  </div>
  
  <div class="team-section">
    <h3 class="team-title">我们的团队</h3>
    <p class="team-subtitle">由行业专家组成的专业团队，为您提供最优质的服务</p>
    
    <div class="team-grid">
      {#each teamMembers as member}
        <div class="team-card">
          <div class="team-image">
            <img src={member.image} alt={member.name} />
          </div>
          <h4 class="team-member-name">{member.name}</h4>
          <p class="team-member-position">{member.position}</p>
          <p class="team-member-description">{member.description}</p>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .about-container {
    display: flex;
    flex-direction: column;
    gap: 3rem;
    margin-bottom: 4rem;
  }
  
  .about-content {
    flex: 1;
  }
  
  .about-description {
    color: #4b5563;
    margin-bottom: 1.5rem;
    line-height: 1.7;
    font-size: 1.125rem;
  }
  
  .stats-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
    margin-top: 2.5rem;
  }
  
  .stat-item {
    text-align: center;
    padding: 1.5rem;
    background-color: #f3f4f6;
    border-radius: 0.5rem;
  }
  
  .stat-value {
    font-size: 2.25rem;
    font-weight: 700;
    color: #3b82f6;
    margin-bottom: 0.5rem;
    font-family: 'Montserrat', sans-serif;
  }
  
  .stat-label {
    color: #4b5563;
    font-weight: 500;
  }
  
  .about-image {
    flex: 1;
    border-radius: 0.5rem;
    overflow: hidden;
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
  }
  
  .about-image img {
    width: 100%;
    height: auto;
    display: block;
  }
  
  .team-section {
    margin-top: 4rem;
  }
  
  .team-title {
    font-size: 1.875rem;
    font-weight: 700;
    text-align: center;
    margin-bottom: 1rem;
    color: #1f2937;
    font-family: 'Montserrat', sans-serif;
  }
  
  .team-subtitle {
    text-align: center;
    color: #4b5563;
    max-width: 600px;
    margin: 0 auto 3rem;
  }
  
  .team-grid {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 2rem;
  }
  
  .team-card {
    background-color: white;
    border-radius: 0.5rem;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    transition: transform 0.3s ease;
  }
  
  .team-card:hover {
    transform: translateY(-5px);
  }
  
  .team-image {
    width: 100%;
    height: 250px;
    overflow: hidden;
  }
  
  .team-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.5s ease;
  }
  
  .team-card:hover .team-image img {
    transform: scale(1.05);
  }
  
  .team-member-name {
    font-size: 1.25rem;
    font-weight: 600;
    margin: 1.5rem 0 0.5rem;
    padding: 0 1.5rem;
    color: #1f2937;
  }
  
  .team-member-position {
    color: #3b82f6;
    font-weight: 500;
    margin-bottom: 1rem;
    padding: 0 1.5rem;
  }
  
  .team-member-description {
    color: #4b5563;
    line-height: 1.6;
    padding: 0 1.5rem 1.5rem;
  }
  
  @media (min-width: 768px) {
    .about-container {
      flex-direction: row;
    }
    
    .stats-container {
      grid-template-columns: repeat(4, 1fr);
    }
    
    .team-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  
  @media (min-width: 1024px) {
    .team-grid {
      grid-template-columns: repeat(3, 1fr);
    }
  }
</style>
