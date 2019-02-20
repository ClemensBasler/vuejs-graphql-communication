<template>
  <div>
    Hi
  </div>

</template>

<script>
import gql from 'graphql-tag'

export default {
  data() {
    return {

    }
  },
  methods: {
    async open() {
      const query = gql `
        query User {
          fruits{name}
        }
      `;
      const response = await fetch('http://localhost:4000', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
          'Accept': 'application/json',
        },
        body: JSON.stringify({
          query,
          variables: {

          },
        })
      });
      const { data } = await response.json()
      console.log(data)
    }
  },
  mounted() {
    this.open()
    console.log("hi");
  }
}
</script>
