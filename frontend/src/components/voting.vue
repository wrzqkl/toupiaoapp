<template>
    <div class="voting-container">
        <div class="card">
            <!-- 顶部状态栏 -->
             <div class="header">
                <div class="status-badge" :class="{connected: isConnected}">
                    <span class="status-bot"></span>
                    {{ isConnected ? '已连接' : '未连接' }}
                </div>
                <div class="account-badge">
                    0x34456787878543456
                </div>
            </div>
            <!-- 标题 -->
            <h1 class="title">区块链投票</h1>
            <p class="subtitle">去中心化、透明、不可篡改</p>
            <!-- 候选人列表票数 -->
            <div class="section">
                <div class="section-header">
                    <h2>当前票数</h2>
                </div>
                <div class="loading-state">
                    <div class="spinner"></div>
                    <span>加载数据中</span>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script setup>
import { ref } from 'vue';
const isConnected = ref(false);
</script>

<style>
.voting-container {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #f3f4f6;
    padding: 20px;
}
.card {
    background: #ffffff;
    width: 100%;
    max-width: 480px;
    border-radius: 20px;
    box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.05), 0 8px 10px -6px rgba(0, 0, 0, 0.01);
    padding: 32px;
    transition: transform 0.2s ease;
}
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 24px;
}
.status-badge {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 13px;
    font-weight: 600;
    color: #6b7280;
    background: #f0fafb;
    padding: 6px 12px;
    border-radius: 999px;
    border: 1px solid #e5e7eb;
}
.status-badge.connected {
    color: #059669;
    background: #ecfdf5;
    border-color: #d1fae5;
}
.status-bot {
    width: 8px;
    height: 8px;
    background: #d1d5db;
    border-radius: 50%;
}
.connected .status-bot {
    background: #10b981;
    box-shadow: 0 0 0 2px rgba(16, 185, 129, 0.2);
}
.account-badge {
    font-size: 12px;
    color: #6b7280;
    background: #f3f4f6;
    padding: 4px 8px;
    border-radius: 6px;
}
.title {   
    font-size: 28px;
    font-weight: 800;
    color: #111827;
    text-align: center;
    margin: 0 0 8px 0;
    letter-spacing: -0.02em;
}
.subtitle {
    text-align: center;
    color: #6b7280;
    font-size: 14px;
    margin-bottom: 32px;
}
.section {
    margin-bottom: 24px;
}
.section-header h2 {
    font-size: 14px;
    letter-spacing: 0.05em;
    color: #9ca3af;
    font-weight: 700;
    margin-bottom: 12px;
}
.loading-state {
    text-align: center;
    padding: 20px;
    color: #9ca3af;
    font-size: 14px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
}
.spinner {
    width: 20px;
    height: 20px;
    border: 2px solid #e5e7eb;
    border-top-color: #2563eb;
    border-radius: 50%;
    animation: spin 0.8s linear infinite;
}

</style>