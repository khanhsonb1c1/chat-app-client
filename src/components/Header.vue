<template>
  <a-layout-header class="header border">
    <a-avatar :size="50" src="" />
    <div>
        <h3>Do Khanh Son</h3>
    </div>
  </a-layout-header>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from "vue";
export default defineComponent({
  setup() {
    const input = ref<string>("");
    return {
      input,
    };
  },
});
</script>

<style scoped lang="scss">
.header {
  height: auto;
  padding: 0 10px;
  background: #fff;
  display: flex;
  align-items: center;

    h3 {
        margin: unset;
        margin-left: 1em;

    }
}
</style>
