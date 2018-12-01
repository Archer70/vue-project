<template>
    <div>
        <div id="messages">
            <Message v-for="message in messages" :messageText="message" />
        </div>
        <form v-on:submit.prevent="submitMessage">
            <input v-model="inputText" placeholder="new message">
            <input type="submit" value="add">
        </form>
    </div>
</template>

<script>
import Message from './components/Message.vue';

export default {
  name: 'app',
  components: {
      Message,
  },
  data() {
      return {
        messages: [
            'first message',
            'second',
            'third',
            'add another one'
        ],
        inputText: ''
      }
  },
  methods: {
      submitMessage() {
          this.messages.push(this.inputText);
          this.inputText = '';
      }
  }
}
</script>

<style>
#messages {
    position: absolute;
    top: 0;
    bottom: 0;
    width: 800px;
    margin: 0 auto;
    padding: 1rem;
}

form {
    position: fixed;
    top: 90%;
}
</style>
