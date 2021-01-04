<template>
  <AppUserList>
    <template #userlist="{list, count}">
      {{ count }}
      <AppUserCardList :list="list" />
    </template>
  </AppUserList>
</template>

<script>
import AppUserList from "@/components/AppUserList";
import AppUserCardList from "@/components/AppUserCardList";

export default {
  components: {
    AppUserList,
    AppUserCardList,
  },
};
</script>
