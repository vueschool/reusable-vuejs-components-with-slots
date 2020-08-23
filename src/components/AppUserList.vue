<template>
  <section>
    <slot name="title">Users</slot>
    <ul class="userlist" v-if="state === 'loaded'">
      <li v-for="item in data.results" :key="item.email">
        <div>
          <img
            width="48"
            height="48"
            :src="item.picture.large"
            :alt="item.name.first + ' ' + item.name.last"
          />
          <div>
            <div>{{ item.name.first }}</div>
          </div>
        </div>
      </li>
    </ul>
    <slot v-if="state === 'loading'" name="loading">
      loading...
    </slot>
    <slot v-if="state === 'failed'" name="error">
      Oops, something went wrong.
    </slot>
  </section>
</template>

<script>
const states = {
  idle: "idle",
  loading: "loading",
  loaded: "loaded",
  failed: "failed"
}

export default {
  data() {
    return {
      state: "idle",
      data: undefined,
      error: undefined,
      states
    }
  },
  mounted() {
    this.load()
  },
  methods: {
    async load() {
      this.state = "loading"
      this.error = undefined
      this.data = undefined
      try {
        const response = await fetch("https://randomuser.me/api/?results=5")
        const json = await response.json()
        this.state = "loaded"
        this.data = json
        return response
      } catch (error) {
        this.state = "failed"
        this.error = error
        return error
      }
    }
  }
}
</script>

<style>
.userlist {
  margin: 10px;
}
.userlist img {
  border-radius: 50%;
  margin-right: 1rem;
}

.userlist li + li {
  margin-top: 10px;
}

.userlist li > div {
  display: flex;
  align-items: center;
}

.userlist li div div {
  flex: 1;
}
</style>
