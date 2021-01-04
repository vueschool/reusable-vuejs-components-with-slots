<template>
  <div class="page">
    <AppUserList>
      <template #userlist="{list}">
        <AppUserCardsList :list="list">
          <template #secondrow="{ item }">
            <h4>{{ item.name.first }}</h4>
          </template>
        </AppUserCardsList>
      </template>
    </AppUserList>
  </div>
</template>

<script>
import AppUserList from "@/components/AppUserList";
import AppUserCardsList from "@/components/AppUserCardsList";
export default {
  components: {
    AppUserList,
    AppUserCardsList,
  },
  data() {
    return {
      selected: "first",
      options: [
        { value: "first", label: "first name" },
        { value: "last", label: "last name" },
        { value: "full", label: "full name" },
        { value: "fullWithTitle", label: "full name with title" },
      ],
    };
  },
};
</script>

<style>
.page {
  padding: 2rem;
}

.page > * + * {
  margin-top: 2rem;
}
</style>
