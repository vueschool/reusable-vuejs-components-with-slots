<template>
  <ul class="userlist">
    <li v-for="item in list" :key="item.email">
      <slot name="listitem" :user="item">
        <div class="card">
          <img
            class="resposive"
            :src="item.picture.large"
            :alt="item.name.first + ' ' + item.name.last"
          />
          <div class="card-body">
            <div>{{ item.name.first }}</div>
            <slot name="secondrow" :item="item"></slot>
          </div>
        </div>
      </slot>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    list: Array,
    default: () => {}
  }
};
</script>

<style scoped>
.userlist {
  display: grid;
  gap: 1rem;
  grid-template-columns: 1fr 1fr 1fr;
}

.resposive {
  width: 100%;
}

.card {
  box-shadow: 0 0 4px rgba(0, 0, 0, 0.25);
  border-radius: 4px;
  overflow: hidden;
}

.card-body {
  padding: 1rem;
}
</style>