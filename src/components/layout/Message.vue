<template>
  <div :class="[message.isAuthor ? 'flex-end' : 'flex-start', 'message']">
    <a-avatar :size="46" :src="message.avatar" v-if="!message.isAuthor" />
    <span
      :class="[
        message.isAuthor ? 'bg-blue-1 color-black' : 'border bg-white color-black',
        'message-content  badge',
      ]"
    >
      {{ message.content }}
    </span>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    message: {
      type: Object,
      required: true,
    },

    background: {
      type: String,
      default: "blue",
    },

    color: {
      type: String,
      default: "black",
    },
  },
  setup(props) {
    const { message } = props;

    return {
      message,
    };
  },
});
</script>

<style scoped lang="scss">
.message {
  display: flex;
  align-items: center;
  margin: 5px 10px;
  .message-content {
    margin-left: 15px;
    padding: 10px;
    max-width: 85%;
  }
}
</style>
