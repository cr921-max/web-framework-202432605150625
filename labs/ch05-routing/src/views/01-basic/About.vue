<template>
  <div class="page-wrapper">
    <div class="about-card">
      <!-- 顶部的装饰图标和标题 -->
      <div class="card-header">
        <div class="icon-box">📚</div>
        <div>
          <h2>About 关于页</h2>
          <p class="subtitle">系统信息说明</p>
        </div>
      </div>

      <!-- 内容区域 (保留了你原本的文字) -->
      <div class="card-body">
        <p>
          我是路由 <span class="code-tag">/about</span> 对应的页面组件。
        </p>
        <p class="muted-text">
          从 Home 点过来：地址栏变成 <span class="code-tag">#/about</span> ，Home 组件被卸载、我被挂进 router-view——组件级切换，不是页面级刷新。
        </p>
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
.about-card {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 32px;
  /* 多层阴影制造悬浮感 */
  box-shadow: 
    0 1px 3px rgba(0, 0, 0, 0.02),
    0 10px 40px -10px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(0, 0, 0, 0.03);
  transition: transform 0.3s ease;
}

.about-card:hover {
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
  background-color: #eff6ff; /* 这里换成了浅蓝色背景，呼应 About 的不同 */
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

/* 底部高亮的提示框 */
.muted-text {
  color: #4b5563 !important;
  font-size: 14px !important;
  background-color: #f8fafc;
  padding: 16px;
  border-radius: 8px;
  border-left: 3px solid #3b82f6; /* 换成蓝色边线，呼应主题 */
  margin-top: 24px !important;
}

/* 高级的粉色代码药丸 */
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
</style>