<template>
  <AppUserList>
    <template #secondrow="{item}">
      <a :href="'tel:' + item.phone"> {{ item.phone }}</a>
      <a :href="'mailto:' + item.email"> {{ item.email }}</a>
    </template>
  </AppUserList>
</template>

<script>
import AppUserList from "@/components/AppUserList";

export default {
  components: {
    AppUserList
  }
};
</script>
