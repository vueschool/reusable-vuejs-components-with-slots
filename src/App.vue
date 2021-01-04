<template>
  <AppUserList>
    <template #secondrow="{item: user, remove}">
      <AppButton @click="remove(user)">remove</AppButton>
    </template>
  </AppUserList>
</template>

<script>
import AppButton from "@/components/AppButton";
import AppUserList from "@/components/AppUserList";
export default {
  components: {
    AppButton,
    AppUserList,
  },
};
</script>
