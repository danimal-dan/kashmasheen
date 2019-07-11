<template>
  <div id="app">
    <div class="columns is-mobile">
      <div class="column">
        <AtmButton side="left" />
      </div>
      <div class="column is-two-thirds">
        <router-view />
      </div>
      <div class="column">
        <AtmButton side="right" />
      </div>
    </div>
  </div>
</template>

<script>
import AtmButton from '@/components/AtmButton.vue';

export default {
  components: {
    AtmButton,
  },
};
</script>

<style lang="scss">
@import '@/assets/style/main.scss';
</style>
