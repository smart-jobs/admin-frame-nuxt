<template>
  <iframe :src="routerPath" frameborder="0" width="100%" height="100%"></iframe>
</template>

<script>
export default {
  head: {
    title: '系统管理',
  },
  async fetch({store, params}) {
    store.commit('naf/menu/NAV_MODULE_SELECTED', params.module);
  },
  mounted() {
    console.log('router:', this.$router);
  },
  data() {
    return {};
  },
  computed: {
    routerPath() {
      const { params } = this.$route;
      const { base } = this.$router.options;
      console.log('params:', params);
      const module = params.module || params[0];
      return `${base}${module}/${params.module?params[0]:''}`;
    },
  },
};
</script>
