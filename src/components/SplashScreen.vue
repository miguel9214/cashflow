<template>
  <div class="splashscreen">
    <img src="@/assets/logo.svg" alt="Logo" />
    <h1><span>Track</span>Cash</h1>
  </div>
</template>

<style scoped>
.splashscreen {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
}
h1 {
  color: var(--brand-blue);
}
h1 span {
  color: var(--brand-green);
}
</style>
