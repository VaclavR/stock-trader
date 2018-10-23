<template>
  <div id="app" class="container">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <router-link tag="a" to="/" class="navbar-brand">Stock Trader</router-link>
      <button class="navbar-toggler" type="button">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <router-link tag="a" to="/portfolio" class="nav-link">Portfolio</router-link>
          </li>
          <li class="nav-item">
            <router-link tag="a" to="/stocks" class="nav-link">Stocks</router-link>
          </li>
        </ul>
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <a class="nav-link">End Day</a>
          </li>
          <li class="nav-item dropdown" :class="{ show: isCollapsed }" @click="toggleDropdown">
            <a class="nav-link dropdown-toggle" id="navbarDropdown">
              Save & Load
            </a>
            <div class="dropdown-menu" :class="{ show: isCollapsed }">
              <a class="dropdown-item">Save Data</a>
              <a class="dropdown-item">Load Data</a>
            </div>
          </li>
          <li class="nav-item">
            <span class="navbar-text font-weight-bold">
              Funds: $10.000
            </span>
          </li>
        </ul>
      </div>
    </nav>
    <router-view/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class App extends Vue {
  // initial data
  private isCollapsed = false;

  // // computed
  // get computedMsg () {
  //   return 'computed ' + this.msg
  // }

  // method
  private toggleDropdown() {
    this.isCollapsed = !this.isCollapsed;
  }
}

</script>


<style lang="scss">
@import '../node_modules/bootstrap/scss/bootstrap.scss';
.dropdown,
.nav-link {
  cursor: pointer;
}
.navbar-text {
  cursor: default;
}
</style>
