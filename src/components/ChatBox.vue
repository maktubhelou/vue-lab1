<template>
  <div class="right">
    <div class="top">
                <span>To:
                    <span class="name"> {{ currentContact }} </span>
                </span>
    </div>
    <div class="chat active-chat">
      <div class="conversation-start">
        <span>Today, 6:48 AM</span>
      </div>
      <div
        class="bubble"
        v-for='message in messages'
        :class="{'me': message.sender === 'me', 'you': message.sender === 'you'}"
        :key='message.time.toString()'>
          {{ message.text }}
        <div class="time">
          {{ message.time.toLocaleDateString() }}
          {{ message.time.toLocaleTimeString() }}
        </div>
      </div>
    </div>
    <div class="write">
      <a href="javascript:;" class="write-link attach"></a>
      <input type="text" placeholder="Your message here" v-model="newMessage.text" @keypress.enter="sendMessage" autofocus/>
      <a href="javascript:;" class="write-link smiley"></a>
      <a href="javascript:;" class="write-link send" @click="sendMessage"></a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatBox',
  props: ['messages', 'currentContact'],
  data () {
    return {
      newMessage: {
        text: '',
        sender: 'me',
        time: ''
      }
    }
  },
  methods: {
    sendMessage () {
      if (this.newMessage.text) {
        this.newMessage.time = new Date()
        this.messages.push(this.newMessage)
        this.newMessage = {
          text: '',
          sender: 'me'
        }
        setTimeout(this.autoRespond, 5000)
      }
    },
    autoRespond () {
      this.messages.push({
        text: 'Thank you',
        sender: 'you',
        time: new Date()
      })
    }
  }
}
</script>

<style scoped>

</style>
