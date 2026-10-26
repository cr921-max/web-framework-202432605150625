<template>
  <div>
    <!-- 标题 -->
    <h3 class="child-title">🛒 我的订单 (/center/orders)</h3>
    
    <!-- 商品列表 (保留了你的真实数据) -->
    <ul class="order-list">
      <li>
        <span class="book-icon">📖</span>
        <span class="item-name">《Vuejs 前端开发实战》</span>
        <span class="item-price">59.8 元</span>
        <span class="item-status status-shipped">已发货</span>
      </li>
      <li>
        <span class="book-icon">⌨️</span>
        <span class="item-name">机械键盘</span>
        <span class="item-price">329 元</span>
        <span class="item-status status-pending">待付款</span>
      </li>
    </ul>
  </div>
</template>

<style scoped>
/* 子组件标题 */
.child-title { 
  margin: 0 0 16px 0; 
  font-size: 18px; 
  color: #111827; 
  font-weight: 700; 
}

/* 订单列表整体样式 */
.order-list {
  list-style: none; /* 去掉默认的圆点 */
  padding: 0;
  margin: 0;
}

/* 每一行订单 */
.order-list li {
  display: flex;
  align-items: center;
  background-color: #ffffff;
  padding: 12px 16px;
  border-radius: 8px;
  margin-bottom: 12px;
  border: 1px solid #e5e7eb;
  box-shadow: 0 1px 2px rgba(0,0,0,0.02);
  transition: all 0.2s;
}

/* 鼠标放上去微微变色 */
.order-list li:hover {
  border-color: #d1d5db;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
}

/* 图标 */
.book-icon {
  font-size: 20px;
  margin-right: 12px;
}

/* 商品名称 */
.item-name {
  flex: 1; /* 占据多余空间，把价格和状态推到右边 */
  color: #374151;
  font-size: 15px;
  font-weight: 500;
}

/* 价格 */
.item-price {
  color: #111827;
  font-weight: 700;
  font-size: 15px;
  margin-right: 16px;
}

/* 订单状态标签（胶囊状） */
.item-status {
  font-size: 12px;
  padding: 4px 10px;
  border-radius: 20px;
  font-weight: 600;
}

/* 已发货状态：绿色 */
.status-shipped {
  background-color: #ecfdf5;
  color: #059669;
  border: 1px solid #a7f3d0;
}

/* 待付款状态：橙色 */
.status-pending {
  background-color: #fff7ed;
  color: #ea580c;
  border: 1px solid #ffedd5;
}
</style>