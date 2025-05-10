<script lang="ts">
  // 表单数据
  let name = $state('');
  let email = $state('');
  let phone = $state('');
  let message = $state('');
  let submitted = $state(false);
  let loading = $state(false);
  
  // 表单提交处理
  function handleSubmit() {
    loading = true;
    
    // 模拟表单提交
    setTimeout(() => {
      loading = false;
      submitted = true;
      
      // 重置表单
      name = '';
      email = '';
      phone = '';
      message = '';
      
      // 5秒后重置提交状态
      setTimeout(() => {
        submitted = false;
      }, 5000);
    }, 1500);
  }
</script>

<section id="contact" class="section">
  <h2 class="section-title">联系我们</h2>
  <p class="section-subtitle">有任何问题或需求，请随时与我们联系，我们将尽快回复您</p>
  
  <div class="contact-container">
    <div class="contact-info">
      <div class="info-card">
        <div class="info-icon">📍</div>
        <h3 class="info-title">地址</h3>
        <p class="info-content">北京市朝阳区科技园区88号</p>
      </div>
      
      <div class="info-card">
        <div class="info-icon">📞</div>
        <h3 class="info-title">电话</h3>
        <p class="info-content">+86 010-12345678</p>
      </div>
      
      <div class="info-card">
        <div class="info-icon">✉️</div>
        <h3 class="info-title">邮箱</h3>
        <p class="info-content">contact@techcompany.com</p>
      </div>
      
      <div class="info-card">
        <div class="info-icon">🕒</div>
        <h3 class="info-title">工作时间</h3>
        <p class="info-content">周一至周五 9:00-18:00</p>
      </div>
    </div>
    
    <div class="contact-form-container">
      {#if submitted}
        <div class="success-message">
          <div class="success-icon">✓</div>
          <h3>消息已发送！</h3>
          <p>感谢您的联系，我们将尽快回复您。</p>
        </div>
      {:else}
        <form class="contact-form" on:submit|preventDefault={handleSubmit}>
          <div class="form-group">
            <label for="name">姓名</label>
            <input 
              type="text" 
              id="name" 
              bind:value={name} 
              required 
              placeholder="请输入您的姓名"
            />
          </div>
          
          <div class="form-group">
            <label for="email">邮箱</label>
            <input 
              type="email" 
              id="email" 
              bind:value={email} 
              required 
              placeholder="请输入您的邮箱"
            />
          </div>
          
          <div class="form-group">
            <label for="phone">电话</label>
            <input 
              type="tel" 
              id="phone" 
              bind:value={phone} 
              placeholder="请输入您的电话号码（选填）"
            />
          </div>
          
          <div class="form-group">
            <label for="message">留言</label>
            <textarea 
              id="message" 
              bind:value={message} 
              required 
              rows="5" 
              placeholder="请输入您的留言内容"
            ></textarea>
          </div>
          
          <button type="submit" class="submit-button" disabled={loading}>
            {#if loading}
              发送中...
            {:else}
              发送消息
            {/if}
          </button>
        </form>
      {/if}
    </div>
  </div>
</section>

<style>
  .contact-container {
    display: flex;
    flex-direction: column;
    gap: 3rem;
  }
  
  .contact-info {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 1.5rem;
  }
  
  .info-card {
    background-color: white;
    padding: 1.5rem;
    border-radius: 0.5rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    text-align: center;
  }
  
  .info-icon {
    font-size: 2rem;
    margin-bottom: 1rem;
  }
  
  .info-title {
    font-size: 1.125rem;
    font-weight: 600;
    margin-bottom: 0.5rem;
    color: #1f2937;
  }
  
  .info-content {
    color: #4b5563;
  }
  
  .contact-form-container {
    background-color: white;
    padding: 2rem;
    border-radius: 0.5rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
  }
  
  .form-group {
    margin-bottom: 1.5rem;
  }
  
  .form-group label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
    color: #1f2937;
  }
  
  .form-group input,
  .form-group textarea {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #d1d5db;
    border-radius: 0.375rem;
    font-size: 1rem;
    transition: border-color 0.3s;
  }
  
  .form-group input:focus,
  .form-group textarea:focus {
    outline: none;
    border-color: #3b82f6;
    box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.2);
  }
  
  .submit-button {
    background-color: #3b82f6;
    color: white;
    font-weight: 500;
    padding: 0.75rem 1.5rem;
    border: none;
    border-radius: 0.375rem;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.3s;
    width: 100%;
  }
  
  .submit-button:hover {
    background-color: #2563eb;
  }
  
  .submit-button:disabled {
    background-color: #93c5fd;
    cursor: not-allowed;
  }
  
  .success-message {
    text-align: center;
    padding: 2rem;
  }
  
  .success-icon {
    font-size: 3rem;
    color: #10b981;
    background-color: rgba(16, 185, 129, 0.1);
    width: 5rem;
    height: 5rem;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 1.5rem;
  }
  
  .success-message h3 {
    font-size: 1.5rem;
    font-weight: 600;
    margin-bottom: 1rem;
    color: #1f2937;
  }
  
  .success-message p {
    color: #4b5563;
  }
  
  @media (min-width: 640px) {
    .contact-info {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  
  @media (min-width: 1024px) {
    .contact-container {
      flex-direction: row;
    }
    
    .contact-info {
      flex: 1;
      grid-template-columns: repeat(2, 1fr);
    }
    
    .contact-form-container {
      flex: 1.5;
    }
  }
</style>
