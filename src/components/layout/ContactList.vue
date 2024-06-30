<template>
  <a-menu v-model:selectedKeys="selectedKeys" mode="inline" class="mt-3">
    <ContactItem v-for="item in data" :key="item.id" :user="item" />
  </a-menu>
</template>
<script lang="ts">
import { computed, ref } from "vue";
import {
  UserOutlined,
  VideoCameraOutlined,
  UploadOutlined,
} from "@ant-design/icons-vue";
import BoxChat from "../../components/layout/BoxChat.vue";
import { contacts } from "../../data/contact";
import ContactItem from "../item/ContactItem.vue";

export default {
  components: {
    UserOutlined,
    VideoCameraOutlined,
    UploadOutlined,
    BoxChat,
    ContactItem
  },
  setup() {
    const selectedKeys = ref<string[]>(["4"]);
    const data = computed(() => contacts);

    return {
      selectedKeys,
      data,
    };
  },
};
</script>
<style scoped>
#components-layout-demo-responsive .logo {
  height: 32px;
  background: rgba(255, 255, 255, 0.2);
  margin: 16px;
}

.site-layout-sub-header-background {
  background: #fff;
}

.site-layout-background {
  background: #fff;
}

[data-theme="dark"] .site-layout-sub-header-background {
  background: #141414;
}
</style>
