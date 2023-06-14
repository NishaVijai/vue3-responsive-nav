<template>
  <header :class="{ 'scrolled-nav': scrolledNav }">
    <nav>
      <section class="branding">
        <img src="@/assets/logo.png" alt="brand logo" />
      </section>

      <ul v-show="!mobile" class="navigation">
        <li>
          <router-link class="link" :to="{ name: 'Home' }">Home</router-link>
        </li>
        <li>
          <router-link class="link" :to="{ name: 'About' }">About</router-link>
        </li>
        <li>
          <router-link class="link" :to="{ name: 'Portfolio' }"
            >Portfolio</router-link
          >
        </li>
        <li>
          <router-link class="link" :to="{ name: 'Contact' }"
            >Contact</router-link
          >
        </li>
      </ul>

      <section class="icon">
        <i
          v-show="mobile"
          class="fa-solid fa-bars"
          :class="{ 'fas fa-window-close': mobileNav }"
          @click="toggleMobileNav"
        >
        </i>
      </section>

      <transition name="mobile-nav">
        <ul v-show="mobileNav" class="dropdown-nav">
          <li>
            <router-link class="link" :to="{ name: 'Home' }">Home</router-link>
          </li>
          <li>
            <router-link class="link" :to="{ name: 'About' }"
              >About</router-link
            >
          </li>
          <li>
            <router-link class="link" :to="{ name: 'Portfolio' }"
              >Portfolio</router-link
            >
          </li>
          <li>
            <router-link class="link" :to="{ name: 'Contact' }"
              >Contact</router-link
            >
          </li>
        </ul>
      </transition>
    </nav>
  </header>
</template>

<script>
export default {
  name: "VNavigation",
  data() {
    return {
      scrolledNav: null,
      mobile: null,
      mobileNav: null,
      windowWidth: null,
    };
  },
  created() {
    window.addEventListener("resize", this.checkScreen);
    this.checkScreen();
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
    },

    updateScroll() {
      const scrollPosition = window.scrollY;
      if (scrollPosition > 50) {
        this.scrolledNav = true;
        return;
      }
      this.scrolledNav = false;
    },

    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 750) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    },
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: rgba(0, 0, 0, 0.8);
  z-index: 1;
  width: 100%;
  position: fixed;
  transition: all 0.5s ease;
  color: #fff;

  nav {
    display: flex;
    flex-direction: row;
    padding: 12px 0;
    transition: all 0.5s ease;
    width: 90%;
    margin: 0 auto;
    position: relative;

    @media (min-width: 1140px) {
      max-width: 1140px;
    }

    ul,
    .link {
      font-weight: 500;
      color: #fff;
      list-style: none;
      text-decoration: none;
    }

    li {
      text-transform: uppercase;
      padding: 16px;
      margin-left: 16px;
    }

    .link {
      font-size: 14px;
      transition: all 0.5s ease;
      padding-bottom: 4px;
      border-bottom: 1px solid transparent;

      &:hover,
      &:focus {
        color: #00afea;
        border-color: #00afea;
      }
    }

    .branding {
      display: flex;
      align-items: center;

      img {
        width: 50px;
        transition: all 0.5 ease;
      }
    }

    .navigation {
      display: flex;
      align-items: center;
      justify-content: flex-end;
      flex: 1;
    }

    .icon {
      display: flex;
      align-items: center;
      position: absolute;
      top: 0;
      right: 24px;
      height: 100%;

      i {
        cursor: pointer;
        font-size: 24px;
        transition: all 0.8s ease;
      }
    }

    .fa-window-close {
      transform: rotate(90deg);
    }

    .dropdown-nav {
      display: flex;
      flex-direction: column;
      align-items: center;
      position: fixed;
      width: 100%;
      max-width: 250px;
      height: 100%;
      background-color: #fff;
      top: 0;
      left: 0;
      padding-top: 4rem;

      li {
        margin-left: 0;

        .link {
          color: #000;
        }
      }
    }

    .mobile-nav-enter-active,
    .mobile-nav-leave-active {
      transition: all 1s ease;
    }

    .mobile-nav-enter-from,
    .mobile-nav-leave-to {
      transform: translateX(-250px);
    }

    .mobile-nav-enter-to {
      transform: translateX(0);
    }
  }
}

.scrolled-nav {
  background-color: #000;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
    0 2px 4px -1px rgba(0, 0, 0, 0.06);

  nav {
    padding: 8px 0;

    .branding {
      img {
        width: 40px;
        box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
          0 2px 4px -1px rgba(0, 0, 0, 0.06);
      }
    }
  }
}
</style>