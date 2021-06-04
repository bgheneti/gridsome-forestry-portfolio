<template>
    <header class="header" :class="[{sticky: $route.path === '/' }, {scrolled: scrolled && $route.path === '/'}]">
        <div class="container">
            <div class="left">
                <g-link :to="{ name: 'home' }" class="home-link">
                    <h3>Banti Gheneti</h3>
                    <img 
                        v-bind:src="logo"
                        :alt="settings.site_name" 
                        class="logo"
                        :class="[{'scrolled-logo': scrolled && $route.path === '/'}]"
                    />
                </g-link>
            </div>
            <nav class="nav right">
                <g-link class="nav__link" to="/index.html">Bio</g-link>
                <!--<g-link class="nav__link" to="/journal">Journal</g-link>-->
                <g-link class="nav__link" to="/links">Links</g-link>
                <g-link class="nav__link" to="https://github.com/bgheneti">Github</g-link>
                <!--<g-link class="nav__link" to="/contact">Say Hi!</g-link>-->
            </nav>
        </div>
    </header>
</template>

<script>
export default {
  data() {
    return {
        scrolled: false,
        logo: require("../../static/tea_pixiedust.gif"),
        settings: require("../../data/theme.json")
    }
  },

  methods: {
    handleScroll () {
      this.scrolled = window.scrollY > 0;
    }
  },
  beforeMount () {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy () {
    window.removeEventListener('scroll', this.handleScroll);
  }

}
</script>

<style scoped>
.header {
    position: relative;
    height: 6rem;
    z-index: 10;
    background-color: hsla(100, 100%, 100%, 0.9);
    transition: height 0.5s ease;
}
.header.scrolled {
    height: 3rem;
}

.header.sticky {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
}
.header > .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 100%;
}
.home-link {
    text-decoration: none;
}
h3 {
    display: inline;
}
.logo {
    vertical-align: sub;
    margin-left: 0.5rem;
    height: 1.5rem;
    transition: opacity 0.5s;
}
.scrolled-logo{
    opacity: 0;
}
.site-name {
    font-size: 0.9rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-decoration: none;
    text-transform: uppercase;   
}
.nav > * {
    font-size: 0.9rem;
    font-weight: 600;
    text-decoration: none;
    margin-top: 4px;
    margin-right: 3rem;
    padding-bottom: 4px;
    border-bottom: 1px solid;
    border-color: transparent;
    transition: border 0.15s;
}
.nav > *:last-of-type {
    margin: 0;
}
.nav > *:hover {
    border-color: inherit;
}
.nav > .active {
    border-color: inherit;
}
</style>
