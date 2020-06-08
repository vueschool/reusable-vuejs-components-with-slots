<template>
  <div class="page">

    <select v-model="selected">
      <option 
        v-for="option in options" 
        :value="option.value" 
        :key="option.value">
        {{option.label}}
      </option>
    </select>


    <AppUserList>
      <template #userlist="{list}">
        <AppUserCardsList :list="list">
          <template #[selected]="{text}">
            <h2>{{text}}</h2>
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
    AppUserCardsList
  },
  data() {
    return {
      selected: 'first',
      options: [
        { value: 'first',  label: 'first name'},
        { value: 'last',  label: 'last name'},
        { value: 'full',  label: 'fullname'},
        { value: 'fullWithTitle',  label: 'fullname with title'},
      ]
    }
  }
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