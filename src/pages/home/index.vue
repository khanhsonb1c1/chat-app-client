<template>
  <a-layout class="chat-app">
    <a-layout-sider
      breakpoint="lg"
      @collapse="onCollapse"
      @breakpoint="onBreakpoint"
      theme="light"
      class="border"
      width="300"
    >
      <div class="logo">
        <img src="../../assets/Logo-Zalo.webp" alt="">
      </div>
      <ContactList />
    </a-layout-sider>
    <a-layout class="flex-column">
      <Header />
      <BoxChat />
    </a-layout>
  </a-layout>
</template>
<script lang="ts">
import { ref } from "vue";
import {
  UserOutlined,
  VideoCameraOutlined,
  UploadOutlined,
} from "@ant-design/icons-vue";
import BoxChat from "../../components/layout/BoxChat.vue";
import ContactList from "../../components/layout/ContactList.vue";
import Header from "../../components/Header.vue";

export default {
  components: {
    UserOutlined,
    VideoCameraOutlined,
    UploadOutlined,
    BoxChat,
    ContactList,
    Header,
  },
  setup() {
    const selectedKeys = ref<string[]>(["4"]);

    const onCollapse = (collapsed: boolean) => {
      console.log(collapsed);
    };

    const onBreakpoint = (broken: boolean) => {
      console.log(broken);
    };

    return {
      selectedKeys,
      onCollapse,
      onBreakpoint,
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

.logo {
  padding: 1em;
  img {
    height: 35px;
    max-width: 100%;
  }
}
</style>
