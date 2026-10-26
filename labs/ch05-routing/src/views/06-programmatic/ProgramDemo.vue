<template>
  <div class="page-wrapper">
    <div class="program-card">
      <!-- 头部 -->
      <div class="card-header">
        <div class="icon-box">🚀</div>
        <div>
          <h2>编程式导航 (5.5)</h2>
          <p class="subtitle">JS 代码跳转演示</p>
        </div>
      </div>

      <div class="card-body">
        <p class="content-line">不用 router-link，用 JS 代码跳——按钮点起来：</p>

        <!-- 按钮操作面板 -->
        <div class="btn-group">
          <button @click="goStr" class="action-btn">
            <span class="btn-num">①</span>
            <span class="btn-title">push 字符串</span>
            <span class="btn-desc">去用户9527</span>
          </button>

          <button @click="goPath" class="action-btn">
            <span class="btn-num">②</span>
            <span class="btn-title">push 对象 path</span>
            <span class="btn-desc">去用户1</span>
          </button>

          <button @click="goName" class="action-btn">
            <span class="btn-num">③</span>
            <span class="btn-title">push 对象 name+params</span>
            <span class="btn-desc">去用户2</span>
          </button>

          <button @click="goQuery" class="action-btn">
            <span class="btn-num">④</span>
            <span class="btn-title">push query 传参</span>
            <span class="btn-desc">去搜索"vue"</span>
          </button>

          <button @click="goReplace" class="action-btn">
            <span class="btn-num">⑤</span>
            <span class="btn-title">replace 替换</span>
            <span class="btn-desc">去About (不留历史)</span>
          </button>

          <button @click="goBroken" class="action-btn broken">
            <span class="btn-num">⑥</span>
            <span class="btn-title">反例: path+params</span>
            <span class="btn-desc">params 会被忽略</span>
          </button>
        </div>

        <!-- 极客终端日志风格 -->
        <div class="terminal-box">
          <p>> 试历史记录：先点①再点⑤，然后按浏览器"后退"——回到的是本页 (replace 把用户9527那条历史顶掉了)。</p>
          <p>> ④之后地址栏是 <span class="code-tag">#/search?kw=vue</span> ，Search 页用 <span class="code-tag">$route.query.kw</span> 取值。</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* 外层包裹 */
.page-wrapper { padding-top: 10px; }

/* 核心卡片 */
.program-card {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 32px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.02), 0 10px 40px -10px rgba(0,0,0,0.08);
  border: 1px solid rgba(0,0,0,0.03);
}

/* 头部 */
.card-header { display: flex; align-items: center; gap: 16px; margin-bottom: 24px; }
.icon-box {
  width: 48px; height: 48px; background-color: #e0e7ff; /* 浅靛蓝色 */
  border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px;
}
h2 { margin: 0; font-size: 24px; color: #111827; font-weight: 700; }
.subtitle { margin: 4px 0 0 0; font-size: 14px; color: #6b7280; font-weight: 500; }
.content-line { line-height: 1.8; font-size: 15px; color: #374151; margin-bottom: 24px; }

/* 🌟 按钮操作面板 🌟 */
.btn-group {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); /* 自动响应式网格 */
  gap: 16px;
  margin-bottom: 32px;
}

.action-btn {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  background-color: #f9fafb;
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  padding: 16px;
  cursor: pointer;
  transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
  text-align: left;
}

/* 按钮内部文字 */
.btn-num { font-size: 14px; font-weight: 700; color: #6366f1; margin-bottom: 8px; }
.btn-title { font-size: 15px; font-weight: 600; color: #111827; margin-bottom: 4px; }
.btn-desc { font-size: 13px; color: #6b7280; }

/* 按钮悬浮动效 */
.action-btn:hover {
  background-color: #ffffff;
  border-color: #6366f1;
  box-shadow: 0 4px 12px rgba(99, 102, 241, 0.1);
  transform: translateY(-3px); /* 浮起 */
}

/* 按钮点击动效 */
.action-btn:active {
  transform: translateY(0) scale(0.97); /* 按下 */
  box-shadow: none;
}

/* 反例按钮专属：红色调 */
.action-btn.broken:hover {
  border-color: #ef4444;
  box-shadow: 0 4px 12px rgba(239, 68, 68, 0.1);
}
.action-btn.broken .btn-num { color: #ef4444; }

/* 🌟 终端日志风格 🌟 */
.terminal-box {
  background-color: #1e293b;
  border-radius: 8px;
  padding: 20px;
  color: #e2e8f0;
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
  font-size: 13px;
  line-height: 1.8;
  border-left: 4px solid #6366f1;
}

.terminal-box p { margin: 0 0 8px 0; }
.terminal-box p:last-child { margin: 0; }

/* 终端里的代码高亮 */
.code-tag {
  background-color: rgba(255, 255, 255, 0.1);
  color: #a5b4fc;
  padding: 2px 6px;
  border-radius: 4px;
  font-family: monospace;
}
</style>