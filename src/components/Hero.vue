<template>
    <div class="hero">
        <div style='width:100%'>
        <div class='hero-txt'>
        <img class='hero-img' :src="image"/>
            <div class="hero-content" v-for="item in settings.hero_content" :key="item.title">
                <div class="hero-title-wrapper"><h2 class="hero-title" v-html="item.title" /></div>
                <p class="hero-subtitle" v-html="item.text" />
            </div>
        </div>
        </div>
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
    padding: 4rem 0 4rem 0;
}

.hero-content {
    padding-bottom: 2em;
}

@media only screen and (max-width: 600px) {
    .hero-txt {
        width: 100%;
            }
}

.hero-title {
    font-size: 3em;
    font-weight: 400;
    margin: 0 0.5em 0 0;
}
.hero-title-wrapper {
    margin: 0px;
    float: left;
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
    color: #555f77;
    text-align: justify;
}

.hero-img {
    width: 45%;
    float: right;
    margin-left: 30px;
}

.hero-subtitle a {
    color: #FF81D8;
}
.hero-title-wrapper {
    display: inline-block;
    margin: 0;
}
</style>
