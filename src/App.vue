<template>
    <div id="main-container">
        <div id="channels">
            Dummy Data
        </div>
        <div id="messages">
            <Message v-for="message in messages" :messageText="message" />
        </div>
        <form v-on:submit.prevent="submitMessage">
            <input v-model="inputText" placeholder="new message" class="msg-box">
            <input type="submit" value="add" class="button">
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
html {
    height: calc(100% - 5px);
}
body {
    color: #FFF;
    padding: 0;
    margin: 0;
    height: calc(100% - 5px);
    background: #f3fafd;
}
#main-container {
    display: flex;
    flex-flow: row wrap;
    height: 100%;
}
#main-container > * {
    flex: 1 100%;
}
#channels {
    background: #10171e;
    flex: 1 auto;
    padding: 5px 10px;
}
#messages {
    background: #15202b;
    flex: 1 75%;
    max-height: inherit;
    overflow: hidden;
    height: calc(100% - 30px);
    overflow: scroll;
    overflow-x: hidden;
}

form {
    padding: 5px;
    height: 30px;
    background: #1E2D3A;
}
.msg-box {
    width: calc(100% - 75px);
    border-radius: 5px;
    height: 25px;
    color: #FFF;
    border: 1px solid #38444d;
    background: #10171e;
    padding: 3px 10px;
}
.button {
    padding: 6px 12px;
    border: none;
    border-radius: 3px;
    float: right;
}
@media screen and (max-width: 720px) {
    #messages {
        order: 1;
    }
    form {
        order: 2;
    }
    #channels {
        order: 3;
    }
}
</style>
