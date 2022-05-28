<template>
  <div class="friends">
    <MainHeader />
    <main class="flex">
      <Sidebar />
      <FriendRequests />
      <Widget />
    </main>
  </div>
</template>

<script>
import MainHeader from "../components/MainHeader.vue";
import FriendRequests from "../components/FriendRequests.vue";
import Widget from "../components/Widget.vue";
export default {
  name: "friends-el",
  components: {
    MainHeader,
    Sidebar,
    FriendRequests,
    Widget,
  },
};
</script>

<style scoped>
</style>