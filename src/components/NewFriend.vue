<template>
  <div class="add_friends">
    <h4 class="title">Add new friend</h4>
    <p class="add_text">Name:</p>
    <input v-model="nameValue" class="add_input" type="text" />
    <p class="add_text">Phone:</p>
    <input v-model="phoneValue" class="add_input" type="text" />
    <p class="add_text">Email:</p>
    <input v-model="emailValue" class="add_input" type="text" />
    <button v-on:click="addFriend" class="btn">Add info</button>
  </div>
</template>

<script>
export default {
  emits: ["add-friend-contact"],
  data() {
    return {
      nameValue: "",
      phoneValue: "",
      emailValue: "",
    };
  },
  methods: {
    addFriend() {
      this.$emit(
        "add-friend-contact",
        this.nameValue,
        this.phoneValue,
        this.emailValue
      );
      this.nameValue = "";
      this.phoneValue = "";
      this.emailValue = "";
    },
  },
};
</script>

<style>
.add_friends {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.title {
  font-size: 24px;
  font-weight: bold;
  margin: 10px auto;
}
.add_text {
  margin: 5px auto;
  font-size: 18px;
}
.add_input {
  width: 200px;
  height: 25px;
  font-size: 18px;
}
</style>
