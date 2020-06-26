<template>
  <div class="hello">
    <h3 class="title">Referrer leak checker</h3>

      <div v-if="openerDetected">
        Window opener detected! <br />
        <button class="button is-small" @click.prevent="modifyOpener">Modify opener</button>
      </div>
      <div v-if="referrer">
        Referrer: {{referrer}}
        <span v-if="secret" class="has-text-danger">
          secret leaked!
        </span>
      </div>
      <div v-else>
        No referrer detected. <a href="https://web-security-demo.web.app/clear">Check this awesome thing! </a>
      </div>
  </div>  
</template>

<script>
export default {
  data() {
    return {
      openerDetected: !!window.opener,
      referrer: document.referrer
    }
  },
  computed: {
    secret() {
      if (!this.referrer) {
        return ''
      }
      const referrerUrl = new URL(this.referrer)
      return referrerUrl.searchParams.get('secret') || ''
    }
  },
  methods: {
    modifyOpener() {
      window.opener.location = 'http://bad-site.web.app/login'
      self.close()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
