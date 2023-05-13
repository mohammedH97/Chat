<script setup>
const props = defineProps(["message"]);
</script>
<template>
  <div
    class="flex rounded my-2 px-2 py-4"
    :class="{
      'justify-end': message.outgoing,
      'bg-sky-500/50': !message.outgoing,
      'bg-[#50d71e]': message.outgoing,
    }"
  >
    <p>{{ message.text }}</p>
  </div>
</template>
