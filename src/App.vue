<template>
  <section>
    <h2>My friends</h2>
    <add-new-friend @add-friend-contact="addFriendcontrol"></add-new-friend>
    <friend-contact
      v-for="friend in friends"
      v-bind:key="friend.id"
      v-bind:id="friend.id"
      v-bind:name="friend.name"
      v-bind:phone-number="friend.phone"
      v-bind:email-address="friend.email"
      v-bind:is-favorite="friend.favorite"
      @toggle-favorite="toggleFavoriteControl"
      @delete="deleteContact"
    ></friend-contact>
  </section>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: "john",
          name: "John Muller",
          phone: "0957 340 509",
          email: "johnmuller@gmail.com",
          favorite: false,
        },
        {
          id: "julia",
          name: "Julia Schwarzkopf",
          phone: "0989 567 154",
          email: "juliaschwarzkopf@gmail.com",
          favorite: false,
        },
        {
          id: "johann",
          name: "Johann Weiss",
          phone: "0254 489 463",
          email: "johannweiss@gmail.com",
          favorite: false,
        },
      ],
    };
  },
  methods: {
    toggleFavoriteControl(favoriteId) {
      const identifiedFriend = this.friends.find(
        (friend) => friend.id === favoriteId
      );
      identifiedFriend.favorite = !identifiedFriend.favorite;
    },
    addFriendcontrol(nameNew, phoneNew, emailNew) {
      const idFriends = nameNew.split(" ")[0].toLowerCase();

      const friendInfo = {
        id: idFriends,
        name: nameNew,
        phone: phoneNew,
        email: emailNew,
        favorite: false,
      };
      this.friends.push(friendInfo);

      console.log(this.friends);
    },
    deleteContact(id) {
      this.friends = this.friends.filter((friend) => friend.id !== id);
    },
  },
};
</script>
<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
section {
  width: 800px;
  height: auto;
  margin: 20px auto;
  border: 2px solid rgba(17, 17, 17, 0.247);
  box-shadow: 0 10px 5px hsla(0, 0%, 7%, 0.13);
}
h2 {
  border: 2px solid #4f105c;
  text-align: center;
  padding: 20px 0;
  background-color: #4f105c;
  color: white;
  font-size: 48px;
  text-transform: uppercase;
}
#app div {
  margin: 10px auto;
  border: 1px solid #4f105c;
  width: 600px;
}
#app li {
  list-style: none;
}
.btn {
  background: #4f105c;
  color: white;
  padding: 10px;
  border: none;
  display: block;
  margin: 10px auto;
}
</style>
