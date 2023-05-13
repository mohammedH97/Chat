<script setup>
import ChatList from "@/components/ChatList.vue";
import { ref } from "vue";
const conversations = ref([]);
conversations.value.push({
  title: "Mohammed Ali chat",
  messages: [
    {
      outgoing: true,
      text: "Hi Mohammed ",
    },
    {
      outgoing: false,
      text: "Hi Hasan",
      username: "hhh",
    },
  ],
});
conversations.value.push({
  title: "Hasan chat",
  messages: [
    {
      outgoing: true,
      text: "Hi Hasan",
    },
    {
      outgoing: false,
      text: "Welcome Mohammed",
    },
  ],
});
</script>
<template>
  <div class="container flex justify-center">
    <chat-list :conversations="conversations"></chat-list>
  </div>
</template>
