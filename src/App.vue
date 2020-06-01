<template>
  <AppLayout>
    <template #header>Slots are great</template>
    <template #default>
      <AppButton @click="log">
        <AppIcon name="heart" />
        add to favorites
      </AppButton>
    </template>
    <template #footer>made with slots</template>
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
    AppIcon
  },
  methods: {
    log() {
      console.log("works");
    }
  }
};
</script>
