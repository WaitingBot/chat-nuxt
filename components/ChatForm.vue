<template>
  <v-flex xs12>
    <v-text-field label="Написать" single-line solo v-model="text"
      @keydown.enter="send"
    ></v-text-field>
  </v-flex>
</template>

<script>
export default {
  data: () => ({
    text: ''
  }),
  methods: {
    send() {
      this.$socket.emit('createMessage', {
        text: this.text,
        id: this.$store.state.user.id
      }, () => {
        if (typeof data === 'string') {
          console.error()
        } else {
          this.text = '';
        }
      })
    }
  }
}
</script>