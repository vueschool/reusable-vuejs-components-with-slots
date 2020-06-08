<template>
  <AppUserList>
    <template #userlist="{list, count, remove}">
      <AppUserCardsList :list="list">
        <template #secondrow="{item}">
          <AppButton @click="remove(item)">remove</AppButton>
        </template>
      </AppUserCardsList>
    </template>
  </AppUserList>
</template>

<script>
import AppButton from "@/components/AppButton";
import AppUserList from "@/components/AppUserList";
import AppUserCardsList from "@/components/AppUserCardsList";
export default {
  components: {
    AppButton,
    AppUserList,
    AppUserCardsList
  }
};
</script>
