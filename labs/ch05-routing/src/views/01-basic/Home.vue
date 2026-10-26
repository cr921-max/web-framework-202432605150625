<template>
  <div class="page-wrapper">
    <div class="home-card">
      <!-- 顶部的装饰图标和标题 -->
      <div class="card-header">
        <div class="icon-box">🏠</div>
        <div>
          <h2>Home 首页</h2>
          <p class="subtitle">路由组件演示</p>
        </div>
      </div>

      <!-- 内容区域 -->
      <div class="card-body">
        <p>
          我是路由 <span class="code-tag">/home</span> 对应的页面组件。
          当地址栏变为 <span class="code-tag">#/home</span> 时，`router-view` 就会在这里渲染我。
        </p>
        <p class="muted-text">
          注意：整个切换过程页面没有刷新（F12 Network 里没有新请求）——这就是"前端路由"的魅力。
        </p>

        <!-- 假装放两个操作按钮，撑起页面的丰满度 -->
        <div class="action-buttons">
          <button class="btn-primary">去体验路由 →</button>
          <button class="btn-secondary">查看文档</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* 外层包裹，增加一点顶部间距 */
.page-wrapper {
  padding-top: 10px;
}

/* 核心卡片：白底、圆角、极简阴影 */
.home-card {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 32px;
  /* 用多层阴影制造悬浮感，比硬边框高级很多 */
  box-shadow: 
    0 1px 3px rgba(0, 0, 0, 0.02),
    0 10px 40px -10px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(0, 0, 0, 0.03);
  transition: transform 0.3s ease;
}

/* 鼠标放上卡片微微浮起 */
.home-card:hover {
  transform: translateY(-2px);
}

/* 头部：图标和标题并排 */
.card-header {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 24px;
}

.icon-box {
  width: 48px;
  height: 48px;
  background-color: #ecfdf5; /* 浅绿色背景 */
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 24px;
}

h2 {
  margin: 0;
  font-size: 24px;
  color: #111827;
  font-weight: 700;
  letter-spacing: -0.5px;
}

.subtitle {
  margin: 4px 0 0 0;
  font-size: 14px;
  color: #6b7280;
  font-weight: 500;
}

/* 文本内容 */
.card-body p {
  line-height: 1.8;
  font-size: 15px;
  color: #374151;
  margin: 0 0 16px 0;
}

.muted-text {
  color: #6b7280 !important;
  font-size: 14px !important;
  background-color: #f9fafb;
  padding: 12px 16px;
  border-radius: 8px;
  border-left: 3px solid #d1d5db;
}

/* 那个高级的粉色代码药丸 */
.code-tag {
  background-color: #fdf2f8;
  color: #db2777;
  padding: 4px 8px;
  border-radius: 6px;
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
  font-size: 13px;
  font-weight: 600;
  border: 1px solid #fbcfe8;
  margin: 0 2px;
}

/* 模拟的操作按钮 */
.action-buttons {
  display: flex;
  gap: 12px;
  margin-top: 32px;
  padding-top: 24px;
  border-top: 1px solid #f3f4f6;
}

.btn-primary {
  background-color: #111827;
  color: #ffffff;
  border: none;
  padding: 10px 20px;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s;
}

.btn-primary:hover {
  background-color: #374151;
}

.btn-secondary {
  background-color: #ffffff;
  color: #374151;
  border: 1px solid #d1d5db;
  padding: 10px 20px;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s;
}

.btn-secondary:hover {
  background-color: #f9fafb;
  border-color: #9ca3af;
}
</style>