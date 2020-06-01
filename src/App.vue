<template>
  <div>
    <AppButton @click="log">
      <AppIcon name="heart" />
      add to favorites
    </AppButton>
  </div>
</template>

<script>
import AppButton from "@/components/AppButton";
import AppIcon from "@/components/AppIcon";

export default {
  components: {
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
