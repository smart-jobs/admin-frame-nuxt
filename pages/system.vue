<template>
  <nuxt-child />
</template>
<script>
export default {
  layout: 'default',
  async fetch({store, $axios}) {
    store.commit('naf/menu/NAV_MODULE_SELECTED', 'system');
  }
};
</script>
