<template>
  <div id="main-root">
    <ul class="mainapp-sidemenu">
      <li @click="push('/purehtml')">子应用4 purehtml app</li>
    </ul>
    <!-- loading -->
    <div v-if="loading">loading</div>
    <!-- 子应用盒子 -->
    <div id="root-view" class="app-view-box" v-html="content"></div>
  </div>
</template>

<script>
export default {
  name: "App",
  props: {
    loading: Boolean,
    content: String
  },
  methods: {
    push(subapp) {
      window.history.pushState(null, subapp, subapp);
    }
  }
};
</script>
