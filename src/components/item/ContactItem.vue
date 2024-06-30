<template>
  <a-menu-item :key="user.id" style="height: unset; padding: 10px 0; border-radius: 0;">
    <a-avatar :size="38" :src="user.avatar" />
    <span class="nav-text ms-2 color-black">{{ user.name  }}</span>
  </a-menu-item>
</template>
<script lang="ts">
export default {
  props: {
    user: {
      type: Object,
      required: true,
    },
  },
  components: {},
  setup() {},
};
</script>
<style scoped lang="scss">
.contact-item {
    padding: 1em;
    height: unset !important;
}

</style>
