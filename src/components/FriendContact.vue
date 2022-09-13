<template>
  <div>
    <li class="name">
      {{ name }} {{ this.isFavoriteChange === "1" ? "(Favorite)" : "" }}
    </li>
    <button class="btn" v-on:click="toggleFavorite">Toggle Favorite</button>
    <button class="btn" v-on:click="toggleDetails">
      {{ detailsIsvisible ? "Hide" : "Show" }} details
    </button>
    <ul v-if="detailsIsvisible">
      <li class="add_info"><strong>Phone: </strong>{{ phoneNumber }}</li>
      <li class="add_info"><strong>Email: </strong>{{ emailAddress }}</li>
    </ul>
  </div>
</template>
<script>
export default {
  props: ["name", "phoneNumber", "emailAddress", "isFavorite"],
  data() {
    return {
      detailsIsvisible: false,
      friends: {
        id: "john",
        name: "John Muller",
        phone: "0957 340 509",
        email: "johnmuller@gmail.com",
      },
      isFavoriteChange: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsIsvisible = !this.detailsIsvisible;
    },
    toggleFavorite() {
      if (this.isFavoriteChange === "1") {
        this.isFavoriteChange = "0";
      } else this.isFavoriteChange = "1";
    },
  },
};
</script>
