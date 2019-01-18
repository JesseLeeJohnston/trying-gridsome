<template>
  <Layout>
    <h1>About Info</h1>
    <ul>
      <li v-for="(item, index) in $page.allFaker.edges" :key="index"> {{ item.node.author }} </li>
    </ul>

        <Pager :info="$page.allFaker.edges"/>
  </Layout>
</template>
<script>
import { Pager } from 'gridsome'

export default {
  components: {
    Pager
  }
  
}
</script>
<page-query>
{
  allFaker (perPage: 10) @paginate {
    edges {
      node {
        author
        email
        avatar
      }
    }
  }
}
</page-query>




