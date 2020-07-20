<template>
    <div class="hero">
        <div style='width:100%'>
        <div class='hero-txt'>
            <h2 class="hero-title" v-html="settings.hero_title" />
            <h2 class="hero-subtitle" v-html="settings.hero_subtitle" />
        </div>
        <div class='hero-img'>
            <img :src="image"/>
        </div>
        </div>
         <span style='clear:left; display: block'></span>
    </div>
</template>

<script>
export default {
  data() {
    var settings = require("../../data/theme.json");
    return {
      settings: settings,
      image: require('../../'.concat(settings.hero_img))
    };
  }
}
</script>

<style>
.hero {
    text-align: left;
    width: 800px;
    max-width: 100%;
    margin: 0 auto;
    padding: 4rem 0 8rem 0;
}

.hero-img {
    width:40%;
    float: left;
}

.hero-txt {
    width:60%;
    float: left; 
    padding-right:2em;
}

@media only screen and (max-width: 600px) {
    .hero-img {
        width: 80%;
            }
    .hero-txt {
        width: 100%;
            }
}

.hero-title {
    font-size: 2rem;
    font-weight: 700;
    padding: 0;
    margin: 0 0 2rem 0;
}
.hero-title p,
.hero-subtitle p {
    margin: 0;
    padding: 0;
}
.hero-subtitle {
    font-size: 1.15em;
    font-weight: 500;
    line-height: 1.68;
    padding: 0;
    margin: 0;
    color: #2B3856;
    opacity: 0.8;
}

.hero-subtitle a {
    color: #FF81D8;
}
</style>
