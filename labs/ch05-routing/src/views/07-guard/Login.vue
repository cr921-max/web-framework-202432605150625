<template>
  <div class="page-wrapper">
    <div class="login-card">
      <!-- 头部 -->
      <div class="card-header">
        <div class="icon-box">🔒</div>
        <div>
          <h2>登录页</h2>
          <p class="subtitle">路由守卫演示</p>
        </div>
      </div>

      <div class="card-body">
        <p class="content-line">
          用户中心 (<span class="code-tag">/center</span>) 是"会员区"—— 没有 token 会被守卫拦到这里。
        </p>

        <p class="status-text">
          当前登录状态：
          <strong class="status-success">已登录 (token 存在)</strong>
        </p>

        <!-- 关键点 1：这里必须绑定 @click="logout" -->
        <button @click="logout" class="btn-danger">
          退出登录 (删 token)
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      // 初始化时检查是否有 token
      isLogin: !!localStorage.getItem('token')
    }
  },
  methods: {
    // 关键点 2：必须有这个方法，并且里面删除了 token
    logout() {
      // 1. 删除本地存储的 token
      localStorage.removeItem('token')
      
      // 2. 更新页面的状态变量（变为 false）
      this.isLogin = false
      
      // 3. 如果你希望退出后直接跳转到首页，可以解开下面这行代码：
      // this.$router.push('/home')
      
      // 这里加个弹窗，让你确认真的点到了
      alert('Token 已删除，您已退出登录！')
    }
  }
}
</script>

<style scoped>
/* (把之前的样式放在这里，保持不变即可) */
.page-wrapper { padding-top: 10px; }
.login-card {
  background-color: #ffffff; border-radius: 16px; padding: 32px; max-width: 500px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.02), 0 10px 40px -10px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(0, 0, 0, 0.03);
}
.card-header { display: flex; align-items: center; gap: 16px; margin-bottom: 24px; }
.icon-box {
  width: 48px; height: 48px; background-color: #fef2f2; border-radius: 12px;
  display: flex; align-items: center; justify-content: center; font-size: 24px;
}
h2 { margin: 0; font-size: 24px; color: #111827; font-weight: 700; }
.subtitle { margin: 4px 0 0 0; font-size: 14px; color: #6b7280; font-weight: 500; }
.content-line { line-height: 1.8; font-size: 15px; color: #374151; margin: 0 0 16px 0; }
.code-tag {
  background-color: #f8fafc; color: #e11d48; padding: 4px 8px; border-radius: 6px;
  font-family: monospace; font-size: 13px; border: 1px solid #e2e8f0;
}
.status-text { font-size: 15px; color: #4b5563; margin-bottom: 24px; }
.status-success { color: #059669; font-weight: 700; }

/* 按钮的悬浮和点击动画 */
.btn-danger {
  background-color: #fef2f2; color: #dc2626; border: 1px solid #fecaca;
  padding: 10px 20px; border-radius: 8px; font-size: 14px; font-weight: 600;
  cursor: pointer; transition: all 0.2s; outline: none;
}
.btn-danger:hover {
  background-color: #fee2e2; color: #b91c1c; transform: translateY(-2px); box-shadow: 0 4px 12px rgba(220, 38, 38, 0.15);
}
.btn-danger:active { transform: translateY(0) scale(0.96); box-shadow: none; }
</style>