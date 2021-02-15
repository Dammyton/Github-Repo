<template>
  <div class="container">
    <div class="tabs">
      <div class="temp__container">
        <div class="temp__info" id="temp-info">
          <img id="temp-thumbnail" alt="" class="temp__thumbnail" />
          <span id="temp-username" class="temp__username"></span>
        </div>
      </div>
      <div class="tab__list">
        <div class="tab overview">
          <img class="tab__icons" inline src="src/assets/book.svg" alt="" />
          <span>Overview</span>
        </div>
        <div class="tab repos">
          <img class="tab__icons" inline src="src/assets/repo.svg" alt="" />
          <span>Repositories</span>
          <span class="counter">{{ repo_count }} </span>
        </div>
        <div class="tab">
          <img class="tab__icons" inline src="src/assets/project.svg" alt="" />
          <span>Projects</span>
        </div>
        <div class="tab">
          <img class="tab__icons" inline src="src/assets/package.svg" alt="" />
          <span>Packages</span>
        </div>
      </div>
    </div>

    <!-- REPO_LIST - START -->
    <div class="repos">
      <div class="repos__content">
        <div class="repos__form">
          <form class="search__form">
            <input
              type="search"
              class="search__input"
              placeholder="Find a repository..."
            />
          </form>

          <div class="repos__buttons">
            <div class="filter__buttons">
              <button class="repos__btn">
                <span>Type:</span> All
                <img inline src="src/assets/down-caret.svg" alt="" />
              </button>
              <button class="repos__btn">
                <span>Language:</span> All
                <img inline src="src/assets/down-caret.svg" alt="" />
              </button>
            </div>

            <button class="repos__btn new__btn">
              <img inline src="src/assets/repo.svg" alt="" />
              New
            </button>
          </div>
        </div>

        <div class="repo__parent" id="repo-container">
          <RepositoryList
            v-for="repo in repos"
            :key="repo.id"
            :name="repo.name"
            :language="repo.language"
            :updated_at="repo.updated_at"
            :stargazers_count="repo.stargazers_count"
            :fork="repo.fork"
            :forks_url="repo.forks_url"
            :description="repo.description"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import RepositoryList from "~/components/RepositoryList.vue";

export default {
  components: {
    RepositoryList,
  },
  data() {
    return {
      repos: [],
      repo_count: "",
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
        "https://api.github.com/users/Dammyton/repos",
        config
      );
      this.repos = res.data;
      this.repo_count = this.repos.length;
      console.log(this.repos);
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style>
</style>
