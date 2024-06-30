<template>
  <div class="chat-input">
    <a-input v-model:value="input" placeholder="Input...">
        <template #prefix></template>
        <template #suffix></template>
    </a-input>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from "vue";
export default defineComponent({
  setup() {
    const input = ref<string>("");
    return {
        input
    };
  },
});
</script>

<style scoped lang="scss">
.chat-input {
  margin: 5px 16px 16px 16px;
}


</style>
