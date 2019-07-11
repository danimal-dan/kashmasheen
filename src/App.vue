<template>
  <div id="app">
    <div class="columns is-mobile">
      <div class="column">
        <button>Yeah</button>
      </div>
      <div class="column is-two-thirds">
        <router-view />
      </div>
      <div class="column">
        <button>Yeah</button>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import '@/assets/style/main.scss';
</style>
