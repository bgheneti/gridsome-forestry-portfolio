<template>
  <Layout>
    <div class="container">
      <Hero />
    </div>
    <!--<LatestJournals :journals="$page.journals.edges" />-->
  </Layout>
</template>

<script>
import Hero from "@/components/Hero"

export default {
  components: {
    Hero
  }
}
</script>
