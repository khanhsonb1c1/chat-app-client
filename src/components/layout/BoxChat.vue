<template>
  <a-layout-content class="box-chat border">
    <div class="box-chat-body">
      <a-flex gap="middle" vertical>
        <Message v-for="mess in data" :key="mess._id" :message="mess" />
      </a-flex>
    </div>
  </a-layout-content>
  <ChatInput />
</template>

<script lang="ts">
import { computed, defineComponent } from "vue";
import Message from "./Message.vue";
import { messageData } from "../../data/message";
import ChatInput from "../input/chatInput.vue";
export default defineComponent({
  name: "BoxChat",

  setup() {
    const data = computed(() => messageData);

    return {
      data,
    };
  },
});
</script>

<style scoped lang="scss">
.box-chat {
  margin: 24px 16px 16px 16px;
  border-radius: 0.5em;
  overflow-y: auto;
  padding: 10px 5px;
  background-color: #fff;

  .box-chat-body {
    padding: "24px";
    margin-bottom: 0.5em;
  }

  /* Custom scrollbar */
  &::-webkit-scrollbar {
    width: 8px; /* Chiều rộng của thanh cuộn */
  }

  &::-webkit-scrollbar-track {
    background: #f1f1f1; /* Màu nền của track */
  }

  &::-webkit-scrollbar-thumb {
    background-color: #888; /* Màu của thanh cuộn */
    border-radius: 10px; /* Bo góc thanh cuộn */
    border: 2px solid #f1f1f1; /* Đường viền xung quanh thanh cuộn */
  }

  &::-webkit-scrollbar-thumb:hover {
    background: #555; /* Màu của thanh cuộn khi hover */
  }
}
</style>
