<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-12 outer-frame">
        <b-navbar toggleable="lg" type="light" variant="info">
          <b-navbar-brand href="#">NavBar</b-navbar-brand>

          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav>
              <b-nav-item href="#">Link</b-nav-item>
              <b-nav-item href="#" disabled>Disabled</b-nav-item>
            </b-navbar-nav>

            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
              <b-nav-form>
                <b-form-input
                  size="sm"
                  class="mr-sm-2"
                  placeholder="Search"
                ></b-form-input>
                <b-button size="sm" class="my-2 my-sm-0" type="submit"
                  >Search</b-button
                >
              </b-nav-form>

              <b-nav-item-dropdown text="Lang" right>
                <b-dropdown-item href="#">EN</b-dropdown-item>
                <b-dropdown-item href="#">ES</b-dropdown-item>
                <b-dropdown-item href="#">RU</b-dropdown-item>
                <b-dropdown-item href="#">FA</b-dropdown-item>
              </b-nav-item-dropdown>

              <b-nav-item-dropdown right>
                <!-- Using 'button-content' slot -->
                <template v-slot:button-content>
                  <em>User</em>
                </template>
                <b-dropdown-item href="#">Profile</b-dropdown-item>
                <b-dropdown-item href="#">Sign Out</b-dropdown-item>
              </b-nav-item-dropdown>
            </b-navbar-nav>
          </b-collapse>
        </b-navbar>
        <div>
          <b-alert variant="danger" v-model="showDismissibleAlert" dismissible>
            Dismissible Alert!
          </b-alert>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-md-2">
        <DraggableComponents />
      </div>
      <div class="col-md-10 no-right">
        <b-tabs content-class="mt-3">
          <b-tab title="First" active><CanvasComponent /></b-tab>
          <b-tab title="Second"><p>I'm the second tab</p></b-tab>
          <b-tab title="Disabled" disabled><p>I'm a disabled tab!</p></b-tab>
        </b-tabs>
      </div>
    </div>
  </div>
</template>

<script>
import DraggableComponents from "./templates/DraggableComponents.vue";
import CanvasComponent from "./templates/CanvasComponent.vue";

export default {
  data() {
    return {
      showDismissibleAlert: true
    };
  },
  components: {
    DraggableComponents,
    CanvasComponent
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.no-right {
  padding-right: 0px !important;
}

.outer-frame {
  padding: 0px !important;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
