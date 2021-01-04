<template>
  <AppLayout>
    <AppButton @click="log">
      <AppIcon name="heart" />
      add to favorites
    </AppButton>
  </AppLayout>
</template>

<script>
import AppLayout from "@/components/AppLayout";
import AppButton from "@/components/AppButton";
import AppIcon from "@/components/AppIcon";

export default {
  components: {
    AppLayout,
    AppButton,
    AppIcon,
  },
  methods: {
    log() {
      console.log("works");
    },
  },
};
</script>
