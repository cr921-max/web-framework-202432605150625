<template>
  <div class="page-wrapper">
    <div class="center-card">
      <!-- 头部 -->
      <div class="card-header">
        <div class="icon-box">🧩</div>
        <div>
          <h2>用户中心 (外壳)</h2>
          <p class="subtitle">嵌套路由演示</p>
        </div>
      </div>

      <div class="card-body">
        <p>
          访问 <span class="code-tag">/center/xxx</span> 时我（外壳）不动，我肚子里的 <span class="code-tag">router-view</span> 换子组件——两级路由各管各的出口。
        </p>

        <!-- 子导航 (专门针对嵌套路由的样式) -->
        <nav class="sub-nav">
          <router-link to="/center/profile" class="sub-nav-btn">个人资料</router-link>
          <router-link to="/center/orders" class="sub-nav-btn">我的订单</router-link>
        </nav>

        <!-- 嵌套路由出口，这里渲染子组件 -->
        <div class="sub-view-container">
          <router-view></router-view>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* 基础卡片样式 (与之前保持一致) */
.page-wrapper { padding-top: 10px; }
.center-card {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 32px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.02), 0 10px 40px -10px rgba(0,0,0,0.08);
  border: 1px solid rgba(0,0,0,0.03);
}
.card-header { display: flex; align-items: center; gap: 16px; margin-bottom: 24px; }
.icon-box {
  width: 48px; height: 48px; background-color: #fef08a; /* 浅黄色底座 */
  border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px;
}
h2 { margin: 0; font-size: 24px; color: #111827; font-weight: 700; }
.subtitle { margin: 4px 0 0 0; font-size: 14px; color: #6b7280; font-weight: 500; }
.card-body p { line-height: 1.8; font-size: 15px; color: #374151; margin-bottom: 24px; }

/* 代码高亮药丸 */
.code-tag {
  background-color: #f8fafc; color: #e11d48; padding: 4px 8px; border-radius: 6px;
  font-family: monospace; font-size: 13px; font-weight: 600; border: 1px solid #e2e8f0;
}

/* 二级导航栏样式 */
.sub-nav {
  display: flex; gap: 12px; margin-bottom: 20px;
  border-bottom: 1px solid #e5e7eb; padding-bottom: 16px;
}
.sub-nav-btn {
  text-decoration: none; color: #4b5563; font-size: 14px; font-weight: 500;
  padding: 8px 16px; border-radius: 8px; transition: all 0.2s; background-color: #f3f4f6;
}
.sub-nav-btn:hover { background-color: #e5e7eb; }
/* 二级导航激活状态 */
.sub-nav-btn.router-link-active {
  background-color: #10b981; color: white; box-shadow: 0 2px 4px rgba(16,185,129,0.3);
}

/* 子页面渲染的容器 (做出内嵌感) */
.sub-view-container {
  background-color: #f9fafb; /* 浅灰底色 */
  padding: 24px; border-radius: 12px; border: 1px dashed #d1d5db;
}
</style>