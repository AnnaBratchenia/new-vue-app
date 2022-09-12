<template>
  <div>
    <li class="name">{{ friends.name }}</li>
    <button class="btn" v-on:click="toggleDetails">
      {{ detailsIsvisible ? "Hide" : "Show" }} details
    </button>
    <ul v-if="detailsIsvisible">
      <li class="add_info"><strong>Phone: </strong>{{ friends.phone }}</li>
      <li class="add_info"><strong>Email: </strong>{{ friends.email }}</li>
    </ul>
  </div>
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
