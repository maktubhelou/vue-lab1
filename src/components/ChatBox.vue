<template>
  <div class="right">
    <div class="top">
                <span>To:
                    <span class="name">Thomas Bangalter</span>
                </span>
    </div>
    <div class="chat active-chat">
      <div class="conversation-start">
        <span>Today, 6:48 AM</span>
      </div>
      <div class="bubble me">
        My first message
      </div>
    </div>
    <div class="write">
      <a href="javascript:;" class="write-link attach"></a>
      <input type="text" placeholder="Your message here" />
      <a href="javascript:;" class="write-link smiley"></a>
      <a href="javascript:;" class="write-link send"></a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatBox'
}
</script>

<style scoped>

</style>
