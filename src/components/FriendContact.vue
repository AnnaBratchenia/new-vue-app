<template>
  <div>
    <li class="name">
      {{ name }} {{ this.isFavoriteChange ? "(Favorite)" : "" }}
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
  // props: ["name", "phoneNumber", "emailAddress", "isFavorite"],
  props: {
    name: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    emailAddress: {
      type: String,
      required: true,
    },
    isFavorite: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  data() {
    return {
      detailsIsvisible: false,
      isFavoriteChange: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsIsvisible = !this.detailsIsvisible;
    },
    toggleFavorite() {
      this.isFavoriteChange = !this.isFavoriteChange;
    },
  },
};
</script>
