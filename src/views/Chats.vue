<template>
  <div class="chats">
    <MainHeader />
    <main class="flex">
      <Sidebar />
      <User v-if="type === 'user'" :uid="id" />
      <Group v-else :guid="id" />
      <Widget />
    </main>
  </div>
</template>

<script>
import MainHeader from "../components/MainHeader.vue";
import User from "../components/User.vue";
import Group from "../components/Group.vue";
import Widget from "../components/Widget.vue";
export default {
  name: "chats-el",
  props: ['id', 'type'],
  setup() {
    return {};
  },
  components: {
    MainHeader,
    Sidebar,
    User,
    Group,
    Widget,
  },
};
</script>

<style scoped>
</style>