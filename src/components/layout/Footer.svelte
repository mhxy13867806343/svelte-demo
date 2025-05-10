<script lang="ts">
  const currentYear = new Date().getFullYear();
  
  // 页脚链接
  const footerLinks = [
    {
      title: '公司',
      links: [
        { text: '关于我们', href: '#about' },
        { text: '团队', href: '#team' },
        { text: '招聘', href: '#careers' },
        { text: '新闻', href: '#news' }
      ]
    },
    {
      title: '服务',
      links: [
        { text: '解决方案', href: '#solutions' },
        { text: '产品', href: '#products' },
        { text: '技术支持', href: '#support' },
        { text: '合作伙伴', href: '#partners' }
      ]
    },
    {
      title: '资源',
      links: [
        { text: '博客', href: '#blog' },
        { text: '案例研究', href: '#case-studies' },
        { text: '白皮书', href: '#whitepapers' },
        { text: '常见问题', href: '#faq' }
      ]
    }
  ];
  
  // 社交媒体链接
  const socialLinks = [
    { icon: '微博', href: '#' },
    { icon: '微信', href: '#' },
    { icon: '知乎', href: '#' },
    { icon: '抖音', href: '#' }
  ];
</script>

<footer class="footer">
  <div class="footer-container">
    <div class="footer-top">
      <div class="footer-brand">
        <h3 class="footer-logo">科技企业</h3>
        <p class="footer-description">
          我们致力于为客户提供最优质的技术解决方案，帮助企业实现数字化转型。
        </p>
        <div class="social-links">
          {#each socialLinks as social}
            <a href={social.href} class="social-link" aria-label={social.icon}>
              {social.icon}
            </a>
          {/each}
        </div>
      </div>
      
      <div class="footer-links-container">
        {#each footerLinks as section}
          <div class="footer-links-section">
            <h4 class="footer-links-title">{section.title}</h4>
            <ul class="footer-links">
              {#each section.links as link}
                <li><a href={link.href}>{link.text}</a></li>
              {/each}
            </ul>
          </div>
        {/each}
      </div>
    </div>
    
    <div class="footer-bottom">
      <div class="copyright">
        &copy; {currentYear} 科技企业. 保留所有权利.
      </div>
      <div class="legal-links">
        <a href="#privacy">隐私政策</a>
        <a href="#terms">服务条款</a>
        <a href="#cookies">Cookie 政策</a>
      </div>
    </div>
  </div>
</footer>

<style>
  .footer {
    background-color: #1f2937;
    color: #f3f4f6;
    padding: 4rem 0 2rem;
  }
  
  .footer-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
  }
  
  .footer-top {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 3rem;
  }
  
  .footer-brand {
    flex: 0 0 100%;
    margin-bottom: 2rem;
  }
  
  .footer-logo {
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 1rem;
    font-family: 'Montserrat', sans-serif;
    color: #3b82f6;
  }
  
  .footer-description {
    max-width: 300px;
    margin-bottom: 1.5rem;
    line-height: 1.6;
    color: #d1d5db;
  }
  
  .social-links {
    display: flex;
    gap: 1rem;
  }
  
  .social-link {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background-color: #374151;
    color: #f3f4f6;
    transition: background-color 0.3s;
    text-decoration: none;
    font-size: 0.875rem;
  }
  
  .social-link:hover {
    background-color: #3b82f6;
  }
  
  .footer-links-container {
    display: flex;
    flex-wrap: wrap;
    flex: 1;
    gap: 2rem;
  }
  
  .footer-links-section {
    flex: 1;
    min-width: 160px;
  }
  
  .footer-links-title {
    font-weight: 600;
    margin-bottom: 1.25rem;
    color: #f9fafb;
  }
  
  .footer-links {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  .footer-links li {
    margin-bottom: 0.75rem;
  }
  
  .footer-links a {
    color: #d1d5db;
    text-decoration: none;
    transition: color 0.3s;
  }
  
  .footer-links a:hover {
    color: #3b82f6;
  }
  
  .footer-bottom {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    padding-top: 2rem;
    border-top: 1px solid #374151;
  }
  
  .copyright {
    font-size: 0.875rem;
    color: #9ca3af;
  }
  
  .legal-links {
    display: flex;
    gap: 1.5rem;
  }
  
  .legal-links a {
    font-size: 0.875rem;
    color: #9ca3af;
    text-decoration: none;
    transition: color 0.3s;
  }
  
  .legal-links a:hover {
    color: #3b82f6;
  }
  
  @media (min-width: 768px) {
    .footer-brand {
      flex: 0 0 300px;
      margin-bottom: 0;
    }
  }
  
  @media (max-width: 768px) {
    .footer-links-container {
      gap: 3rem;
    }
    
    .footer-bottom {
      flex-direction: column;
      gap: 1rem;
      text-align: center;
    }
    
    .legal-links {
      justify-content: center;
    }
  }
</style>
