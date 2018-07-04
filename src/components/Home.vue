<template>
  <div class="wrapper">
    <div class="container">
      <ContactList></ContactList>
      <ChatBox></ChatBox>
    </div>
  </div>
</template>

<script>
import ChatBox from './ChatBox'
import ContactList from './ContactList'

export default {
  name: 'Home',
  components: {
    ChatBox,
    ContactList
  }
}
</script>

<style scoped>

</style>
