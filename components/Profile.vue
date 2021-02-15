<template>
  <div class="profile">
    <div class="profile__info" id="profile-info">
      <div class="about">
        <div class="avatar" id="profile-avatar">
          <img id="profile__img" :src="data.avatar_url" alt="profile pic" />
        </div>

        <div class="metadata">
          <h1 class="name">{{ data.name }}</h1>
          <h3 class="username">{{ data.login }}</h3>
        </div>

        <button class="edit__btn">Edit profile</button>
        <div class="social__metrics">
          <span
            ><img src="../assets/people.svg" alt="" />
            <span>{{ data.followers }}</span> followers</span
          >
          &nbsp;&middot;&nbsp;
          <span
            ><span>{{ data.following }}</span> following</span
          >
          &nbsp;&middot;&nbsp;
          <span> <img src="../assets/star.svg" alt="" /> <span>11</span> </span>
        </div>
        <ul class="meta__list">
          <li class="meta__info">
            <img src="../assets/law.svg" alt="" /> {{ data.location }}
          </li>
          <li class="meta__info">
            <img src="../assets/book.svg" alt="" /> {{ data.blog }}
          </li>
          <li class="meta__info">
            <img src="../assets/people.svg" alt="" />
            {{ data.twitter_username }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      data: "",
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };
    try {
      const res = await axios.get(
        "https://api.github.com/users/Dammyton",
        config
      );
      this.data = res.data;
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style>

</style>
