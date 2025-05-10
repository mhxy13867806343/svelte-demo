<script lang="ts">
  // 定义列表项的类型
  interface ListItem {
    id: number;
    title: string;
    description: string;
    imageUrl?: string;
  }

  // 示例数据
  let items: ListItem[] = [
    {
      id: 1,
      title: '项目一',
      description: '这是第一个项目的描述信息',
      imageUrl: 'https://picsum.photos/100/100?random=1'
    },
    {
      id: 2,
      title: '项目二',
      description: '这是第二个项目的描述信息',
      imageUrl: 'https://picsum.photos/100/100?random=2'
    },
    {
      id: 3,
      title: '项目三',
      description: '这是第三个项目的描述信息',
      imageUrl: 'https://picsum.photos/100/100?random=3'
    },
    {
      id: 4,
      title: '项目四',
      description: '这是第四个项目的描述信息',
      imageUrl: 'https://picsum.photos/100/100?random=4'
    }
  ];

  // 添加新项目的函数
  function addItem() {
    const newId = items.length > 0 ? Math.max(...items.map(item => item.id)) + 1 : 1;
    items = [...items, {
      id: newId,
      title: `新项目 ${newId}`,
      description: '点击编辑按钮修改此描述',
      imageUrl: `https://picsum.photos/100/100?random=${newId + 4}`
    }];
  }

  // 删除项目的函数
  function removeItem(id: number) {
    items = items.filter(item => item.id !== id);
  }
</script>

<div class="item-list-container">
  <h2>精美列表展示</h2>
  
  <div class="controls">
    <button class="add-button" on:click={addItem}>添加项目</button>
  </div>
  
  <div class="item-list">
    {#each items as item (item.id)}
      <div class="list-item">
        {#if item.imageUrl}
          <img src={item.imageUrl} alt={item.title} class="item-image" />
        {/if}
        <div class="item-content">
          <h3>{item.title}</h3>
          <p>{item.description}</p>
          <div class="item-actions">
            <button class="action-button edit">编辑</button>
            <button class="action-button delete" on:click={() => removeItem(item.id)}>删除</button>
          </div>
        </div>
      </div>
    {/each}
  </div>
</div>

<style>
  .item-list-container {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    font-family: 'Arial', sans-serif;
  }

  h2 {
    color: #333;
    text-align: center;
    margin-bottom: 20px;
    font-size: 1.8rem;
  }

  .controls {
    display: flex;
    justify-content: flex-end;
    margin-bottom: 20px;
  }

  .add-button {
    background-color: #4CAF50;
    color: white;
    border: none;
    padding: 10px 15px;
    border-radius: 4px;
    cursor: pointer;
    font-size: 14px;
    transition: background-color 0.3s;
  }

  .add-button:hover {
    background-color: #45a049;
  }

  .item-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
  }

  .list-item {
    border: 1px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s, box-shadow 0.3s;
    background-color: white;
  }

  .list-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
  }

  .item-image {
    width: 100%;
    height: 150px;
    object-fit: cover;
  }

  .item-content {
    padding: 15px;
  }

  .item-content h3 {
    margin: 0 0 10px 0;
    color: #333;
    font-size: 1.2rem;
  }

  .item-content p {
    margin: 0 0 15px 0;
    color: #666;
    font-size: 0.9rem;
    line-height: 1.4;
  }

  .item-actions {
    display: flex;
    justify-content: flex-end;
    gap: 10px;
  }

  .action-button {
    border: none;
    padding: 6px 12px;
    border-radius: 4px;
    cursor: pointer;
    font-size: 12px;
    transition: background-color 0.3s;
  }

  .action-button.edit {
    background-color: #2196F3;
    color: white;
  }

  .action-button.edit:hover {
    background-color: #0b7dda;
  }

  .action-button.delete {
    background-color: #f44336;
    color: white;
  }

  .action-button.delete:hover {
    background-color: #d32f2f;
  }

  @media (max-width: 600px) {
    .item-list {
      grid-template-columns: 1fr;
    }
  }
</style>