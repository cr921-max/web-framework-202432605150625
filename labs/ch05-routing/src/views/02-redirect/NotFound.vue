<template>
  <div class="page-wrapper">
    <div class="not-found-card">
      <!-- 顶部的装饰图标和标题 -->
      <div class="card-header">
        <div class="icon-box">🪐</div>
        <div>
          <h2>404 | 页面不存在</h2>
          <p class="subtitle">找不到你要访问的页面</p>
        </div>
      </div>

      <!-- 内容区域 (保留原文字) -->
      <div class="card-body">
        <p>
          你访问的地址是：<span class="code-tag">{{ $route.fullPath }}</span>
        </p>
        <p class="muted-text">
          路由表里从上往下找不到能匹配的规则，最后落到我这条通配符路由上。
        </p>

        <!-- 将原本丑陋的超链接换成精致的按钮 -->
        <div class="action-buttons">
          <router-link to="/home" class="btn-primary">
            ← 回首页
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
.not-found-card {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 32px;
  box-shadow: 
    0 1px 3px rgba(0, 0, 0, 0.02),
    0 10px 40px -10px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(0, 0, 0, 0.03);
  transition: transform 0.3s ease;
}

.not-found-card:hover {
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
  background-color: #fef2f2; /* 404 页面用浅红色底座，带点警告意味 */
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

/* 文本 */
.card-body p {
  line-height: 1.8;
  font-size: 15px;
  color: #374151;
  margin: 0 0 16px 0;
}

/* 代码高亮药丸 */
.code-tag {
  background-color: #fdf2f8;
  color: #db2777;
  padding: 4px 8px;
  border-radius: 6px;
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
  font-size: 13px;
  font-weight: 600;
  border: 1px solid #fbcfe8;
  margin: 0 4px;
}

/* 底部提示框 */
.muted-text {
  color: #6b7280 !important;
  font-size: 14px !important;
  background-color: #f9fafb;
  padding: 16px;
  border-radius: 8px;
  border-left: 3px solid #ef4444; /* 404 页面用红色边线 */
  margin: 24px 0 !important;
}

/* 操作按钮区域 */
.action-buttons {
  display: flex;
  margin-top: 32px;
  padding-top: 24px;
  border-top: 1px solid #f3f4f6;
}

/* 按钮样式（把原来的 <a> 标签变成了好看的按钮） */
.btn-primary {
  display: inline-block;
  background-color: #111827;
  color: #ffffff;
  text-decoration: none;
  padding: 10px 24px;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 500;
  transition: all 0.2s;
}

.btn-primary:hover {
  background-color: #374151;
  transform: translateY(-1px);
}
</style>