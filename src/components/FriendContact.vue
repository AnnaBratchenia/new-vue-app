<template>
  <div>
    <li class="name">{{ name }} {{ isFavorite ? "(Favorite)" : "" }}</li>
    <button class="btn" v-on:click="toggleFavorite">Toggle Favorite</button>
    <button class="btn" v-on:click="toggleDetails">
      {{ detailsIsvisible ? "Hide" : "Show" }} details
    </button>
    <button class="btn" v-on:click="$emit('delete', id)">Delete</button>
    <ul v-if="detailsIsvisible">
      <li class="add_info"><strong>Phone: </strong>{{ phoneNumber }}</li>
      <li class="add_info"><strong>Email: </strong>{{ emailAddress }}</li>
    </ul>
  </div>
</template>
<script>
export default {
  emits: ["toggle-favorite", "delete"],
  // props: ["name", "phoneNumber", "emailAddress", "isFavorite"],
  props: {
    id: {
      type: String,
      required: true,
    },
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
    };
  },
  methods: {
    toggleDetails() {
      this.detailsIsvisible = !this.detailsIsvisible;
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.id);
    },
  },
};
</script>
<style>
.name {
  font-size: 36px;
  text-align: center;
  padding-top: 10px;
}
.add_info {
  font-size: 24px;
  text-align: center;
}
.add_info:last-child {
  margin-bottom: 20px;
}
</style>
