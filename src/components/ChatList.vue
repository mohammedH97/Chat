<script setup>
import { computed, ref } from "vue";
import ChatBubble from "@/components/ChatBubble.vue";
const props = defineProps({
  conversations: {
    type: [Array],
    required: true,
  },
});
const selectedConversationIndex = ref();
const currentConversation = computed(() => {
  return props.conversations[selectedConversationIndex.value];
});
</script>
<template>
  <div class="flex gap-2 text-black w-full m-4">
    <div class="flex flex-col w-1/5 bg-indigo-500 rounded p-3">
      <div
        @click="selectedConversationIndex = index"
        v-for="(conversation, index) in conversations"
        class="p-1 rounded m-1 cursor-pointer hover:bg-indigo-100"
      >
        <span class="font-bold">{{ conversation.title }}</span>
      </div>
    </div>
    <div class="flex flex-col w-4/5 bg-[#44403c] rounded h-[90vh]">
      <div v-if="currentConversation != null" class="flex flex-col w-full px-2">
        <chat-bubble
          v-for="message in currentConversation.messages"
          :message="message"
        ></chat-bubble>
      </div>
      <div v-else class="justify-center items-center h-full w-full">
        <span class="rounded text-lg font-bold flex justify-center m-10 bg-[#fef9c3]">Select The Conversation to show it.</span>
      </div>
    </div>
  </div>
</template>
