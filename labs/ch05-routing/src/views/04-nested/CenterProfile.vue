<template>
  <div>
    <h3 class="child-title">📄 个人资料 (/center/profile)</h3>
    <p class="child-text">姓名：张三 | 求职意向：前端开发工程师</p>
    <p class="child-text">
      我是 Center 的 child，地址 <span class="code-tag">/center/profile</span> 里开头的 <span class="code-tag">/center</span> 部分归外壳管。
    </p>
  </div>
</template>

<style scoped>
.child-title { margin: 0 0 16px 0; font-size: 18px; color: #111827; font-weight: 600; }
.child-text { line-height: 1.8; font-size: 14px; color: #4b5563; margin: 0 0 12px 0; }
.code-tag {
  background-color: #ffffff; color: #db2777; padding: 2px 6px; border-radius: 4px;
  font-family: monospace; font-size: 13px; border: 1px solid #fbcfe8;
}
</style>