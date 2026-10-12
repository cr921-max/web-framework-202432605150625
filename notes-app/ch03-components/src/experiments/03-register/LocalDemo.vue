<template>
  <div class="mini">
    <h3>局部注册</h3>
    <p>我在 App.vue 的 <b>components 选项</b>里注册，只有 App 能用我。</p>
  </div>
</template>

<script>
export default {
  name: 'LocalDemo'
}
</script>

<style scoped>
.mini {
  border: 1px dashed var(--border);
  border-radius: 8px;
  padding: 10px 14px;
}
</style>
