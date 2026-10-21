<template>
  <div class="lab">
    <h2>实验 05｜props 父传子（3.5）</h2>
    <p class="muted">PriceBox 用<b>对象方式</b>声明 props（type/required/default）；点按钮故意传错类型，看 Console 警告。</p>

    <div class="pair">
      <PriceBox :price="price" :count="count" />
      <PriceBox :price="price" :count="badCount" />
    </div>

    <p>当前 count = {{ count }}（正常 Number）｜badCount = {{ badCount }}（故意传错，看 Console）</p>
    <button @click="count++">count +1</button>
    <button @click="badCount = badCount === 'abc' ? 'xyz' : 'abc'">换一个错误类型</button>

    <p class="muted">⚠️</p>
  </div>
</template>

<script>
import PriceBox from './PriceBox.vue'

export default {
  name: 'PropsLab',
  components: { PriceBox },
  data() {
    return {
      price: 3999,
      count: 2,
      badCount: 'abc'
    }
  }
}
</script>

<style scoped>
.lab {
  background: var(--card, #fff);
  border: 1px solid var(--border);
  border-left: 4px solid var(--accent);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  padding: 14px 18px;
}

.pair {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin: 8px 0;
}

.muted {
  color: var(--muted);
}
</style>