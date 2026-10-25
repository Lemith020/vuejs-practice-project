<script setup>
import profilePhoto from './assets/profile.jpg'
const name = 'Lemith'
const description = 'Software Engineering Undergraduate'
</script>

<template>
  <main>
    <div class="profile-card">
      <h1>{{ name }}</h1>
      <p>{{ description }}</p>
    </div>
  </main>
</template>

<style scoped>
main {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #eef2ff;
}

.profile-card {
  width: 300px;
  padding: 32px;
  background-color: white;
  border-radius: 20px;
  text-align: center;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
}

h1 {
  margin: 0 0 12px;
  color: #1e293b;
}

p {
  margin: 0;
  color: #64748b;
}
</style>