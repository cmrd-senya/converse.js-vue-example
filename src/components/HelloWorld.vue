<template>
  <div>
    JID: <input type="text" v-model="login"><br>
    Password: <input type="text" v-model="password"><br>
    <button v-on:click="onConnect">Connect</button>
  </div>
</template>

<script>
import '@converse/headless';

export default {
  data () {
    return {
      login: "",
      password: ""
    }
  },
  
  methods: {
    onConnect() {
      window.converse.initialize({
          bosh_service_url: 'https://conversejs.org/http-bind/', // Please use this connection manager only for testing purposes
          jid: this.login,
          auto_login: true,
          password: this.password
      });
    }
  }
}
</script>

