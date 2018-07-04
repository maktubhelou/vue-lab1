<template>
  <div class="wrapper">
    <div class="container">
      <div class="left">
        <div class="top">
          <input type="text" />
          <a href="javascript:;" class="search"></a>
        </div>
        <ul class="people">
          <li 
            v-for="(person, index) in contacts" 
            :key="index" class="person" 
            :class="{'active': person.active}" 
            @click="selectContact(index)"
          >
              <img :src="`https://source.unsplash.com/64x64/?${person.image}`" alt="" />
              <span class="name">{{ person.name }}</span>
              <span class="time">{{ person.time }}</span>
              <span class="preview">{{ person.preview }}</span>
          </li>
        </ul>
      </div>      
      <ChatBox :currentContact="contacts[currentContact].name" :messages="contacts[currentContact].messages"/>
    </div>
  </div>
</template>

<script>
import ChatBox from './ChatBox'

export default {
  name: 'Home',
  data () {
    return {
      currentContact: 0,
      contacts: [
        {
          name: 'Thomas Bangalter',
          image: 'person',
          time: '2:09 PM',
          preview: 'I was wondering...',
          active: true,
          messages: [
            { 
              text: 'Hello',
              sender: 'me',
              time: new Date(2018, 3, 22, 5, 23, 20, 0),
            },
            {
              text: 'What are you doing?',
              sender: 'me',
              time: new Date(2018, 3, 22, 5, 23, 25, 10),
            }
          ]
        },
        {
          name: 'Mark Evans',
          image: 'dog',
          time: '4:09 PM',
          preview: 'Vue.js is awesome...',
          active: false,
          messages: [
            { 
              text: 'Yo',
              sender: 'me',
              time: new Date(2018, 4, 24, 10, 33, 35, 0)
            },
            {
              text: 'Sup?',
              sender: 'me',
              time: new Date(2018, 4, 24, 10, 33, 40, 0)
            },
            {
              text: 'Why so silent?',
              sender: 'me',
              time: new Date(2018, 4, 24, 10, 33, 50, 0)
            },
          ]
        },
        {
          name: 'Denise Thomson',
          image: 'queen',
          time: '4:09 PM',
          preview: 'What you on about?',
          active: false,
          messages: [
            { 
              text: 'Have you eaten yet?',
              sender: 'me',
              time: new Date(2018, 5, 20, 14, 15, 14, 0)
            },
            {
              text: 'Let\'s grab a bite?',
              sender: 'me',
              time: new Date(2018, 5, 20, 14, 15, 26, 0)
            },
          ]
        }
      ]
    }
  },
  components: {
    ChatBox,
  },
  methods: {
    selectContact(index) {
      const lastContact = this.currentContact;
      this.currentContact = index;
      this.contacts[index].active = true;
      this.contacts[lastContact].active = false;
    }
  }
}
</script>

<style scoped>

</style>
