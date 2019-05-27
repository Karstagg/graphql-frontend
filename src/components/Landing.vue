<template>
  <div>
    <ul v-for="user in allPosts">
      <li>内容：　{{user.email}}</li>
    </ul>
  </div>
</template>

<script>
  import gql from 'graphql-tag'

  const POSTS_QUERY = gql`
query allPosts{
  allUsers {
    title
    content
  }
}`;

  export default {
    name: 'index',
    data () {
      return {
        allPosts: []
      }
    },
    apollo: {
      allPosts: {
        query:POSTS_QUERY
      }
    }
  }

</script>