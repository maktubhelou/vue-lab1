<template>
  <div class="left">
    <div class="top">
      <input type="text" />
      <a href="javascript:;" class="search"></a>
    </div>
    <ul class="people">
      <li class="person active">
        <img src="@/assets/img/profile.jpg" alt="" />
        <span class="name">Thomas Bangalter</span>
        <span class="time">2:09 PM</span>
        <span class="preview">I was wondering...</span>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'ContactList'
  }
</script>

<style scoped>

</style>
