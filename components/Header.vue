<template>
  <div class="header">
    <button class="hamburger__btn" id="mobile-menu">
      <img class="hamburger" inline src="../assets/hamburger.svg" alt="" />
    </button>
    <img class="logo" src="../assets/header.png" alt="" />
    <div class="nav__content" id="nav-menu">
      <form class="nav__search">
        <input placeholder="Search or jump to..." />
        <img src="../assets/search-slash.svg" alt="" />
      </form>
	  
      <nav role="navigation" class="nav">
        <ul>
          <li class="nav-link-hide-on-desktop"><a href="#">Dashboard</a></li>
          <li><a href="#">Pull requests</a></li>
          <li><a href="#">Issues</a></li>
          <li><a href="#">Marketplace</a></li>
          <li><a href="#">Explore</a></li>
          <li class="nav-link-hide-on-desktop">
            <a href="#">
              <img id="nav-thumbnail" alt="" class="avatar__thumbnail" />
              <span id="nav-username" class="nav__username"></span>
            </a>
          </li>
          <li class="nav-link-hide-on-desktop">
            <a href="#">
              <img
                class="sign__out"
                inline
                src="../assets/sign-out.svg"
                alt=""
              />
              Sign out</a
            >
          </li>
        </ul>
      </nav>
    </div>

    <div class="notifications">
      <img class="bell" src="../assets/bell.svg" inline alt="" />
      <span class="dot"></span>
    </div>

    <div class="site__links">
      <button class="dropdown__btn" id="site-links-btn">
        <img inline src="../assets/plus.svg" alt="" />
        <img inline src="../assets/down-caret.svg" alt="" />
      </button>
    </div>

    <div class="settings">
      <button class="dropdown__btn" id="settings-btn">
        <img
          id="thumbnail"
          alt=""
          src="https://avatars.githubusercontent.com/u/44869245?v=4"
          class="avatar__thumbnail"
        />
        <img inline src="../assets/down-caret.svg" alt="" />
      </button>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.header {
  background-color: var(--header-bg-color);
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  padding: 0.8em 1em;
  color: #ffffb3;
}

.hamburger__btn {
  display: flex;
  align-items: center;
  padding-left: 0;
  background: none;
}

.hamburger {
  fill: #ffffffb3;
  width: 2em;
  padding: 0.4em;
  padding-left: 0;
}

.logo {
  width: 1.9em;
}

.nav__content {
  order: 10;
  flex: 1 1 746px;
  margin-top: 1.2em;
  display: none;
}

.nav__open {
  display: block;
}

.nav__search {
  display: flex;
  background-color: var(--color-text-primary);
  border: 1px solid var(--border-alternate-color);
  box-shadow: none;
  border-radius: 6px;
  align-items: center;
  font-size: inherit;
  font-weight: 400;
  padding: 6px 12px;
  margin-bottom: 1em;
}

.nav__search input {
  flex: 1;
  font-size: 0.9rem;
  font-weight: 500;
  color: #ffffffcc;
  background: none;
  border: 0;
  box-shadow: none;
  outline: none;
}

.nav__search input::placeholder {
  color: #ffffffcc;
}

.nav {
  margin-left: 0;
}

.nav ul {
  display: flex;
  flex-direction: column;
  color: #fff;
}

.nav li {
  font-size: 0.95rem;
  font-weight: 500;
  white-space: nowrap;
  border-top: 1px solid #ffffff26;
  padding: 0.5em 0em;
}
.nav a {
  display: flex;
  align-items: center;
}

.nav a .nav__username {
  margin-left: 0.4em;
}

.nav a .sign__out {
  width: 1em;
  margin-right: 0.3em;
  fill: #fff;
}

.nav li a:hover {
  color: #ffffffb3;
}

.notifications {
  position: relative;
  display: flex;
  align-items: center;
  cursor: pointer;
}

.notifications .bell {
  fill: #fff;
  width: 1em;
}
.notifications:hover .bell {
  fill: #ffffffb3;
}

.notifications .dot {
  display: inline-block;
  width: 14px;
  height: 14px;
  background-image: linear-gradient(#54a3ff, #006eed);
  position: absolute;
  border: 2px solid var(--color-text-primary);
  border-radius: 50%;
  top: -6px;
  left: 6px;
}

.site__links {
  margin-left: 1.2em;
  position: relative;
  display: none;
}

.settings {
  margin-left: 1em;
  position: relative;
  display: none;
}

.settings .dropdown {
  min-width: 12em;
  padding: 1em 0em;
}

.settings li {
  padding: 0 1em;
}

.settings .sign__in {
  border-bottom: 1px solid var(--border-color);
  padding: 0 1em 0.7em;
  font-size: 0.9rem;
  margin: 0;
}

.sign__in strong {
  display: block;
}

@media (min-width: 868px) {
  .header {
    flex-wrap: nowrap;
    padding-left: 2em;
    padding-right: 2em;
  }

  .hamburger__btn {
    display: none;
  }

  .nav__content {
    display: flex;
    align-items: center;
    order: 0;
    margin-top: 0;
    margin-left: 1.1em;
    margin-right: auto;
  }

  .nav__search {
    flex: 1;
    max-width: 18em;
    margin-bottom: 0;
  }

  .nav-link-hide-on-desktop {
    display: none;
  }

  .nav {
    margin-left: 1.4em;
  }

  .nav ul {
    flex-direction: row;
  }

  .nav li {
    margin-right: 1em;
    border: none;
  }

  .settings,
  .site__links {
    display: block;
    white-space: nowrap;
  }

  .settings svg,
  .site__links svg {
    fill: #fff;
  }
}
</style>