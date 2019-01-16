<template>
  <Layout>
    <h1>About Info</h1>
    <ul>
      <li v-for="(item, index) in $page.allFaker.edges" :key="index"> {{ item.node.author }} </li>
    </ul>
  </Layout>
</template>

<page-query>
{
  allFaker (perPage: 5){
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



<script>
export default {}
</script>
