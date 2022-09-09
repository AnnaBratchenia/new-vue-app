<template>
  <li>{{ friends.name }}</li>
  <button v-on:click="toggleDetails">Show details</button>
  <ul v-if="detailsIsvisible">
    <li><strong>Phone: </strong>{{ friends.phone }}</li>
    <li><strong>Email: </strong>{{ friends.email }}</li>
  </ul>
</template>
<script>
export default {
  data() {
    return {
      detailsIsvisible: false,
      friends: {
        id: "john",
        name: "John Muller",
        phone: "0957 340 509",
        email: "johnmuller@gmail.com",
      },
    };
  },
  methods: {
    toggleDetails() {
      this.detailsIsvisible = !this.detailsIsvisible;
    },
  },
};
</script>
