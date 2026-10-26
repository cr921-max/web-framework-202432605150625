<template>
  <div class="page-wrapper">
    <div class="search-card">
      <!-- 头部：图标和标题 -->
      <div class="card-header">
        <div class="icon-box">🔍</div>
        <div>
          <h2>搜索结果</h2>
          <p class="subtitle">Query 参数演示</p>
        </div>
      </div>

      <!-- 内容区域 -->
      <div class="card-body">
        <!-- 关键词显示 -->
        <p class="content-line">
          关键词：<strong class="highlight-keyword">{{ $route.query.kw }}</strong>
          <span class="from-text">(来自 <span class="code-tag">$route.query.kw</span>)</span>
        </p>

        <!-- 提示框 -->
        <div class="muted-box">
          地址栏 <span class="code-tag">#/search?kw=vue</span> —— query 参数明晃晃挂在问号后面，刷新也不丢。
        </div>

        <!-- 操作按钮 -->
        <div class="action-buttons">
          <!-- 把你原本的 <router-link> 改成这个带样式的按钮 -->
          <router-link to="/program" class="btn-secondary">
            ← 回驾驶舱再传一个
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* 外层包裹 */
.page-wrapper {
  padding-top: 10px;
}

/* 核心卡片 */
.search-card {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 32px;
  box-shadow: 
    0 1px 3px rgba(0, 0, 0, 0.02),
    0 10px 40px -10px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(0, 0, 0, 0.03);
  transition: transform 0.3s ease;
}

.search-card:hover {
  transform: translateY(-2px);
}

/* 头部 */
.card-header {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 24px;
}

.icon-box {
  width: 48px;
  height: 48px;
  background-color: #e0f2fe; /* 浅蓝色底座，代表搜索 */
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

/* 文本样式 */
.content-line {
  line-height: 1.8;
  font-size: 15px;
  color: #374151;
  margin: 0 0 16px 0;
}

/* 突出显示的关键词 */
.highlight-keyword {
  font-size: 18px;
  color: #0284c7; /* 亮蓝色 */
  margin: 0 4px;
  font-weight: 700;
}

.from-text {
  font-size: 14px;
  color: #6b7280;
}

/* 代码高亮药丸 */
.code-tag {
  background-color: #f8fafc;
  color: #475569;
  padding: 4px 8px;
  border-radius: 6px;
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
  font-size: 13px;
  font-weight: 500;
  border: 1px solid #e2e8f0;
}

/* 提示框 */
.muted-box {
  color: #6b7280;
  font-size: 14px;
  background-color: #f9fafb;
  padding: 16px;
  border-radius: 8px;
  border-left: 3px solid #d1d5db;
  margin-bottom: 24px;
}

/* 操作按钮区域 */
.action-buttons {
  display: flex;
  margin-top: 32px;
  padding-top: 24px;
  border-top: 1px solid #f3f4f6;
}

/* 次要按钮 */
.btn-secondary {
  display: inline-block;
  background-color: #ffffff;
  color: #374151;
  text-decoration: none;
  padding: 10px 20px;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 500;
  border: 1px solid #d1d5db;
  transition: all 0.2s;
}

.btn-secondary:hover {
  background-color: #f9fafb;
  border-color: #9ca3af;
  color: #111827;
}
</style>