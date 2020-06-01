<template>
  <AppUserList>
    <template #userlist="{list, count}">
      {{ count }}
      <AppUserCardsList :list="list" />
    </template>
  </AppUserList>
</template>

<script>
import AppUserList from "@/components/AppUserList";
import AppUserCardsList from "@/components/AppUserCardsList";
export default {
  components: {
    AppUserList,
    AppUserCardsList
  }
};
</script>
