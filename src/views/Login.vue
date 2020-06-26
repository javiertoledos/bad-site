<template>
  <div class="pwned">
    <div class="columns is-centered">
      <form class="column is-half-desktop" @submit.prevent="pwned">
        <h1 class="title is-1">Login</h1>
        <div class="field">
          <label class="label" for="email">Email</label>
          <div class="control">
            <input v-model.trim="email" class="input" type="email" required placeholder="email@example.com" id="email" />
          </div>
        </div>
        <div class="field">
          <label class="label" for="password">Password</label>
          <div class="control">
            <input v-model.trim="password" class="input" type="password" required placeholder="****" id="password" />
          </div>
        </div>
        <div class="control">
          <button class="button is-link" type="submit">Login</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    pwned() {
      alert(`Pwned password ${this.password}`);
    }
  }
}
</script>