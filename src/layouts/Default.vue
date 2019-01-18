<template>
  <div class="layout">
    <header class="header">
      <strong>
        <g-link :to="{ name: 'home' }">{{ $static.metaData.siteName }}</g-link>
      </strong>
      <nav class="nav">
        <g-link class="nav__link" :to="{ name: 'home' }">Home</g-link>
        <g-link class="nav__link" :to="{ name: 'about' }">About</g-link>
        <a href="#" class="nav__link" @click.prevent="menuPanel = true">Menu</a>
      </nav>
    </header>
    <slot/>

    <div class="menu-panel" v-bind:class="{active : menuPanel}">
      <div class="heading">
        <h3>Heading <a href="#"><span class="close" @click.prevent="menuPanel = false">Close</span></a></h3>
      </div>
      <div class="body">
           This is the menu panel
           Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex omnis optio pariatur deleniti quisquam minima maxime nesciunt! Minima, nam ratione! Voluptates vel nostrum quaerat aliquam, totam tempore perferendis atque modi!
           Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex omnis optio pariatur deleniti quisquam minima maxime nesciunt! Minima, nam ratione! Voluptates vel nostrum quaerat aliquam, totam tempore perferendis atque modi!
           Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex omnis optio pariatur deleniti quisquam minima maxime nesciunt! Minima, nam ratione! Voluptates vel nostrum quaerat aliquam, totam tempore perferendis atque modi!
           Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex omnis optio pariatur deleniti quisquam minima maxime nesciunt! Minima, nam ratione! Voluptates vel nostrum quaerat aliquam, totam tempore perferendis atque modi!
      </div>
      <div class="footer">
        <h3>Footer</h3>
      </div>
    </div>


  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>
<script>
export default {
  data() {
    return {
      menuPanel: false,
    }
  }
}
</script>

<style>
body {
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
}

.menu-panel {
  position: fixed;
  top: 0px;
  right: 0px;
  width: 350px;
  height: 100%;
  background-color: #222222;
  color: #ffffff;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transform: translateX(350px);
  transition: transform 300ms ease-in-out; 
}
.menu-panel.active {
  transform: translateX(0px)
}
.menu-panel > .body {
  padding: 1rem 0.5rem;
  flex-grow: 1;
  overflow-y: scroll;
}
.menu-panel > .heading {
  padding: 0 0.5rem;
  background-color: rgba(255,255,255,0.1);
}
.menu-panel > .heading .close {
  float: right;
  color: #ffffff;
}
.menu-panel > .footer {
  padding: 0 0.5rem;
  background-color: rgba(255,255,255,0.1);
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}
</style>
