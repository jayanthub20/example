<script setup lang="ts">
import { practice } from '@/routes';

import { ref } from 'vue';

const open = ref(false);

defineOptions({
    layout: {
        breadcrumbs: [
            {
                title: 'Practice',
                href: practice(),
            },
        ],
    },
});
</script>

<template>
  <div class="page-wrapper">
    <!-- Header -->
    <div class="header">
      <div class="logo">Logo</div>
      <div class="search">Search</div>
      <div class="bell">
        🔔
        <span class="badge">7</span>
      </div>
      <div class="avatar-container">
        <button class="avatar" @click="open = !open">
            Avatar ▼
        </button>

        <div v-if="open" class="dropdown">
            <div>Profile</div>
            <div>Settings</div>
            <div>Logout</div>
        </div>
      </div>
    </div>

    <!-- Body -->
    <div class="body">
      <div class="sidebar">
        <div class="dashboard">Dashboard</div>
        <div class="orders">Orders</div>
        <div class="products">Products</div>
        <div class="settings">Settings</div>
      </div>
      <div class="content">
        <div class="cards">
            <div class="card">Card 1</div>
            <div class="card">Card 2</div>
            <div class="card">Card 3</div>
            <div class="card">Card 4</div>
        </div>

        <div class="floating-btn">
            Button
        </div>
      </div>
    </div>
  </div>

  <div class="css-grid">
    <div class="box">1</div>
    <div class="box">2</div>
    <div class="box">3</div>
    <div class="box">4</div>
    <div class="box">5</div>
  </div>
</template>

<style scoped>
/* Full page wrapper stacks header and body vertically */
.page-wrapper {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

/* Header sits at the top, logo on left, profile on right */
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  background: lightblue;
  border: 1px solid black;
  height: 70px;
}

.bell {
    position: relative;
    font-size: 27px;
}

.badge {
    position: absolute;
    top: -5px;
    right: -5px;

    width: 20px;
    height: 20px;
    font-size: 15px;

    border-radius: 50%;
    background: red;
    color: white;

    display: flex;
    justify-content: center;
    align-items: center;
}

.avatar-container {
    position: relative;
    display: inline-block;
}

.avatar {
    padding: 10px 20px;
}

.dropdown {
    position: absolute;
    top: 100%;
    right: 0;
    z-index: 1000;

    width: 150px;

    border: 1px solid black;
    background: white;

    display: flex;
    flex-direction: column;
}

.search {
    flex: 1;
    margin: 0 20px;
}

/* Body fills remaining height, sidebar + content side by side */
.body {
  display: flex;
  flex: 1;              /* takes up all space below the header */
  border: 1px solid black;
}

.sidebar {
  display: flex;
  flex-direction: column;
  gap: 10px;
  flex-shrink: 0;
  width: 250px;         /* fixed sidebar width */
  background: lightblue;
  border-right: 1px solid black;
  padding: 20px;
}

.content {
  flex: 1;              /* fills all remaining width */
  background: rgb(146, 136, 136);
  padding: 20px;
  position: relative;
}

.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    width: 200px;
    height: 150px;
    border: 1px solid black;
}

.floating-btn {
    position: absolute;
    right: 20px;
    bottom: 20px;

    width: 60px;
    height: 60px;

    display: flex;
    justify-content: center;
    align-items: center;

    border: 1px solid black;
}

.css-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-auto-rows: 150px;
    gap: 20px;
}

.box {
    border: 1px solid black;
}
</style>