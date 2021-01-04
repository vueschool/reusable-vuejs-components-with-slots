<template>
  <AppUserList>
    <template #secondrow="{item}">
      <a :href="'phone:' + item.email">{{ item.email }}</a> <br />
      <button>remove</button>
    </template>
  </AppUserList>
</template>

<script>
import AppUserList from "@/components/AppUserList";
export default {
  components: {
    AppUserList,
  },
};
</script>
