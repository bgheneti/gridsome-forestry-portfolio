<template>
  <Layout>
    <div class="container" style="margin-top: 10em">
      <ProjectsGrid :projects="$page.projects.edges" />
    </div>
    <!--<LatestJournals :journals="$page.journals.edges" />-->
  </Layout>
</template>

<page-query>
query Posts {
	projects: allProjectPost {
    edges {
      node {
        id
        date (format: "YYYY")
        title
        categories
        thumbnail (quality: 90)
        path
      }
    }
  },
  journals: allJournalPost (perPage: 4) {
    edges {
      node {
        id
        path
        title
      }
    }
  }
}
</page-query>

<script>
import ProjectsGrid from "@/components/ProjectsGrid"
import LatestJournals from "@/components/LatestJournals"

export default {
  components: {
    ProjectsGrid,
    LatestJournals
  }
}
</script>
