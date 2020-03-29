<template>
  <header>
    <nav class="navbar">
      <span class="navbar-toggle" id="js-navbar-toggle" v-on:click="toggleMenu">
        <div></div>
        <div></div>
        <div></div>
      </span>
      <h1 class="logo">LillyDoo</h1>
      <ul class="main-nav" id="js-menu">
        <li>
          <router-link to="/">Home</router-link>
        </li>
        <li>
          <router-link to="/about">About</router-link>
        </li>
        <li>
          <router-link to="/service">Services</router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
  methods: {
    toggleMenu() {
      let x = document.getElementById("js-menu");
      if (x.className === "main-nav") {
        x.className += " active";
      } else {
        x.className = "main-nav";
      }
    }
  }
};
</script>

<style lang='scss' scoped>
header {
  height: 100px;

  .navbar {
    @include set-background($primary-color);
    /*     background-image: linear-gradient(
      1980deg,
      $primary-color 85%,
      $strip-color 15%
    );
 */
    display: flex;
    justify-content: space-between;
    padding-bottom: 0;
    align-items: center;

    .main-nav {
      list-style-type: none;
      display: flex;
      margin-right: 30px;
      flex-direction: row;
      justify-content: flex-end;

      li {
        margin: 0;
      }

      a {
        color: set-text-color($primary-color);
        margin-left: 40px;
        text-decoration: none;
        cursor: pointer;
      }

      a.router-link-exact-active {
        color: $secondary-color;
      }

      a:hover {
        color: $secondary-color;
      }
    }

    .navbar-toggle {
      display: none;
    }

    .logo {
      font-size: 40px;
      line-height: 2.2;
      text-transform: uppercase;
      display: inline-block;
      margin-left: 20px;
    }
  }
}

@media (max-width: 700px) {
  header {
    height: auto;

    .navbar {
      display: block;
      padding-bottom: 10px;

      .main-nav {
        display: none;
        margin-right: 0;

        li {
          text-align: center;
          margin: 15px auto;
        }

        router-link {
          margin-left: 0;
        }
      }

      .navbar-toggle {
        display: block;
        position: absolute;
        top: 10px;
        right: 20px;
        cursor: pointer;
        color: rgba(255, 255, 255, 0.8);
        font-size: 24px;

        & div {
          width: 35px;
          height: 5px;
          background-color: $light-color;
          margin: 6px 0;
        }
      }

      .active {
        display: block;
      }

      .logo {
        display: inline-block;
        font-size: 22px;
        line-height: 1.5;
        margin-top: 10px;
      }
    }
  }
}
</style>