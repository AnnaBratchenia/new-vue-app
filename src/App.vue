<template>
  <section>
    <h2>My friends</h2>
    <friend-contact
      name="Johnas Borman"
      phone-number="0985 356 265"
      email-address="johnas@gmail.com"
      is-favorite="1"
    ></friend-contact>
    <friend-contact
      name="Johann Weiss"
      phone-number="0658 452 111"
      email-address="johann@gmail.com"
      is-favorite="0"
    ></friend-contact>
  </section>
</template>

<script>
export default {
  data() {
    return {};
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
