<template>
  <div class="page-wrapper">
    <div class="users-card">
      <!-- 头部 -->
      <div class="card-header">
        <div class="icon-box">👥</div>
        <div>
          <h2>用户列表</h2>
          <p class="subtitle">动态路由匹配演示</p>
        </div>
      </div>

      <div class="card-body">
        <p class="content-line">
          路由规则只有一条 <span class="code-tag">/user/:id</span>，却能匹配下面所有用户页——<span class="code-tag">:id</span> 是"占位符"。
        </p>

        <!-- 链接列表改造 -->
        <div class="link-list">
          <!-- 写法 1 -->
          <router-link to="/user/1" class="list-item">
            <span class="item-text">写法① 字符串：用户 1</span>
            <span class="arrow">→</span>
          </router-link>

          <!-- 写法 2 -->
          <router-link to="/user/2" class="list-item">
            <span class="item-text">写法② 拼接变量：用户 2 <span class="tag-id">(id 在 data 里)</span></span>
            <span class="arrow">→</span>
          </router-link>

          <!-- 写法 3 -->
          <router-link :to="{ path: '/user/9527' }" class="list-item">
            <span class="item-text">写法③ 对象 path：用户 9527</span>
            <span class="arrow">→</span>
          </router-link>
        </div>

        <!-- 底部提示 -->
        <div class="muted-box">
          点任意一个：地址栏变 <span class="code-tag">#/user/几</span>，右侧 User 页显示"用户ID：几"。
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
.users-card {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 32px;
  box-shadow: 
    0 1px 3px rgba(0, 0, 0, 0.02),
    0 10px 40px -10px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(0, 0, 0, 0.03);
  transition: transform 0.3s ease;
}

.users-card:hover {
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
  background-color: #e0e7ff; /* 浅紫蓝色底座 */
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

/* 代码高亮药丸 */
.code-tag {
  background-color: #f8fafc;
  color: #e11d48;
  padding: 4px 8px;
  border-radius: 6px;
  font-family: ui-monospace, monospace;
  font-size: 13px;
  font-weight: 500;
  border: 1px solid #e2e8f0;
}

/* 🌟 链接列表改造的核心 🌟 */
.link-list {
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-bottom: 24px;
}

/* 每一行菜单 */
.list-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #f9fafb;
  padding: 16px 20px;
  border-radius: 8px;
  border: 1px solid #e5e7eb;
  text-decoration: none; /* 去掉下划线 */
  color: #3b82f6; /* 默认蓝色文字 */
  font-size: 15px;
  font-weight: 500;
  transition: all 0.2s ease;
}

/* 小标签样式 */
.tag-id {
  font-size: 13px;
  color: #9ca3af;
  font-weight: 400;
  margin-left: 4px;
}

/* 箭头默认隐藏，悬浮时出现 */
.arrow {
  color: #9ca3af;
  font-weight: bold;
  opacity: 0;
  transform: translateX(-10px);
  transition: all 0.2s ease;
}

/* 鼠标悬浮在菜单行上时：整体变色、浮起、背景变白 */
.list-item:hover {
  background-color: #ffffff;
  border-color: #3b82f6;
  color: #1d4ed8; /* 文字变深蓝 */
  transform: translateX(6px); /* 向右滑动 */
  box-shadow: 0 4px 12px rgba(59, 130, 246, 0.1);
}

/* 悬浮时箭头显现 */
.list-item:hover .arrow {
  opacity: 1;
  transform: translateX(0);
}

/* 底部提示框 */
.muted-box {
  color: #6b7280;
  font-size: 14px;
  background-color: #f8fafc;
  padding: 16px;
  border-radius: 8px;
  border-left: 3px solid #cbd5e1;
}
</style>