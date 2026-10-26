<template>
  <div class="page-wrapper">
    <div class="detail-card">
      <!-- 头部 -->
      <div class="card-header">
        <div class="icon-box">🆔</div>
        <div>
          <h2>用户详情</h2>
          <p class="subtitle">动态路由参数演示</p>
        </div>
      </div>

      <!-- 内容区域 -->
      <div class="card-body">
        <p class="content-line">
          用户ID：<strong class="highlight-id">{{ $route.params.id }}</strong> 
          <span class="from-text">(来自 <span class="code-tag">$route.params.id</span>)</span>
        </p>
        
        <div class="muted-box">
          从用户 1 直接点去用户 2：地址变了、参数也变了——但组件没有重新创建（看下面的观看次数）。
        </div>
        
        <p class="content-line viewed-line">
          本组件被复用观看了 
          <!-- 这里加了 String() 兜底，防止 undefined 导致样式塌陷 -->
          <span class="badge">{{ String(viewed || 1) }}</span> 
          次（mounted 只跑一次；参数变化走 watch）
        </p>

        <div class="action-buttons">
          <router-link to="/users" class="btn-secondary">
            ← 回用户列表
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'User',
  data() {
    return { viewed: 1 }
  },
  mounted() {
    console.log('User 组件挂载了：', this.$route.params.id)
  },
  watch: {
    // 监听路由参数变化
    '$route.params.id'(newId) {
      console.log('参数变了：', newId)
      // 每次切换参数，让次数自增
      this.viewed++
    }
  }
}
</script>

<style scoped>
/* 所有样式保持之前的极简风 */
.page-wrapper { padding-top: 10px; }
.detail-card {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 32px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.02), 0 10px 40px -10px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(0, 0, 0, 0.03);
  transition: transform 0.3s ease;
}
.detail-card:hover { transform: translateY(-2px); }
.card-header { display: flex; align-items: center; gap: 16px; margin-bottom: 24px; }
.icon-box {
  width: 48px; height: 48px; background-color: #f3f4f6;
  border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px;
}
h2 { margin: 0; font-size: 24px; color: #111827; font-weight: 700; letter-spacing: -0.5px; }
.subtitle { margin: 4px 0 0 0; font-size: 14px; color: #6b7280; font-weight: 500; }
.content-line { line-height: 1.8; font-size: 15px; color: #374151; margin: 0 0 16px 0; }
.highlight-id { font-size: 20px; color: #e11d48; margin: 0 4px; font-weight: 700; }
.from-text { font-size: 14px; color: #6b7280; }
.code-tag {
  background-color: #f8fafc; color: #475569; padding: 4px 8px; border-radius: 6px;
  font-family: ui-monospace, monospace; font-size: 13px; border: 1px solid #e2e8f0;
}
.muted-box {
  color: #6b7280; font-size: 14px; background-color: #f9fafb;
  padding: 16px; border-radius: 8px; border-left: 3px solid #d1d5db; margin-bottom: 24px;
}
.viewed-line { display: flex; align-items: center; gap: 8px; font-weight: 500; }
.badge {
  display: inline-flex; align-items: center; justify-content: center;
  background-color: #ecfdf5; color: #10b981; padding: 2px 12px;
  border-radius: 20px; font-weight: 700; font-size: 16px;
  border: 1px solid #a7f3d0; min-width: 32px; height: 28px;
}
.action-buttons { display: flex; margin-top: 32px; padding-top: 24px; border-top: 1px solid #f3f4f6; }
.btn-secondary {
  display: inline-block; background-color: #ffffff; color: #374151;
  text-decoration: none; padding: 10px 20px; border-radius: 8px;
  font-size: 14px; font-weight: 500; border: 1px solid #d1d5db; transition: all 0.2s;
}
.btn-secondary:hover { background-color: #f9fafb; border-color: #9ca3af; color: #111827; }
</style>