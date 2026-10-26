<template>
  <div class="page-wrapper">
    <div class="named-card">
      <!-- 头部 -->
      <div class="card-header">
        <div class="icon-box">🔖</div>
        <div>
          <h2>命名路由 (5.4)</h2>
          <p class="subtitle">Path 与 Name 的对比</p>
        </div>
      </div>

      <div class="card-body">
        <p class="content-line">同一个目标，两种写法：</p>

        <!-- 写法对照区域 -->
        <div class="comparison-list">
          <!-- 写法 1 -->
          <router-link to="/user/9527" class="comparison-item">
            <div class="item-title">路径写法：</div>
            <div class="item-code"><span class="code-tag">to="/user/9527"</span></div>
            <div class="item-desc">——直观，但路径写死了</div>
            <span class="arrow">→</span>
          </router-link>

          <!-- 写法 2 -->
          <router-link :to="{ name: 'user', params: { id: 9527 } }" class="comparison-item">
            <div class="item-title">命名写法：</div>
            <div class="item-code"><span class="code-tag">:to="{ name: 'user', params: { id: 9527 } }"</span></div>
            <div class="item-desc">——按 name 找路由，参数交给 params</div>
            <span class="arrow">→</span>
          </router-link>
        </div>

        <!-- 底部提示 -->
        <div class="muted-box">
          好在"改路径"的时候：把路由表里 <span class="code-tag">/user/:id</span> 改成 <span class="code-tag">/member/:id</span>，路径写法全断、命名写法照常——跳转与路径解耦。
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
.named-card {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 32px;
  box-shadow: 
    0 1px 3px rgba(0, 0, 0, 0.02),
    0 10px 40px -10px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(0, 0, 0, 0.03);
  transition: transform 0.3s ease;
}

.named-card:hover {
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
  background-color: #fff7ed; /* 浅橙色底座 */
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
  margin: 0 0 24px 0;
}

/* 🌟 对照卡片样式 🌟 */
.comparison-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  margin-bottom: 24px;
}

.comparison-item {
  position: relative;
  display: flex;
  flex-direction: column;
  background-color: #f9fafb;
  padding: 20px;
  border-radius: 12px;
  border: 1px solid #e5e7eb;
  text-decoration: none;
  transition: all 0.2s ease;
}

/* 标题 */
.item-title {
  font-size: 15px;
  font-weight: 600;
  color: #111827;
  margin-bottom: 8px;
}

/* 代码块行 */
.item-code {
  margin-bottom: 8px;
}

/* 描述文字 */
.item-desc {
  font-size: 14px;
  color: #6b7280;
}

/* 悬浮效果 */
.comparison-item:hover {
  background-color: #ffffff;
  border-color: #f97316; /* 橙色边框 */
  box-shadow: 0 4px 12px rgba(249, 115, 22, 0.1);
  transform: translateX(6px);
}

/* 悬浮时出现的箭头 */
.arrow {
  position: absolute;
  right: 20px;
  top: 50%;
  transform: translateY(-50%) translateX(-10px);
  font-size: 20px;
  color: #f97316;
  opacity: 0;
  transition: all 0.2s ease;
}

.comparison-item:hover .arrow {
  opacity: 1;
  transform: translateY(-50%) translateX(0);
}

/* 代码高亮药丸 */
.code-tag {
  background-color: #fff7ed; /* 浅橙色背景 */
  color: #ea580c; /* 橙色文字 */
  padding: 4px 8px;
  border-radius: 6px;
  font-family: ui-monospace, monospace;
  font-size: 13px;
  font-weight: 500;
  border: 1px solid #ffedd5;
  word-break: break-all; /* 防止长代码撑破卡片 */
}

/* 底部提示框 */
.muted-box {
  color: #6b7280;
  font-size: 14px;
  background-color: #f8fafc;
  padding: 16px;
  border-radius: 8px;
  border-left: 3px solid #cbd5e1;
  line-height: 1.8;
}
</style>