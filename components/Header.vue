<template>
  <div class="container-fluid">
    <div>
      <b-sidebar id="sidebar-1" title="Menu" shadow>
        <b-list-group>
          <b-list-group-item>{{ menu1 }}</b-list-group-item>
          <b-list-group-item v-b-toggle.sidebar-2>{{
            menu2
          }}</b-list-group-item>
          <b-list-group-item v-b-toggle.sidebar-3>{{
            menu3
          }}</b-list-group-item>
          <b-list-group-item v-b-toggle.sidebar-4>{{
            menu4
          }}</b-list-group-item>
          <b-list-group-item v-b-toggle.sidebar-5>{{
            menu5
          }}</b-list-group-item>
          <b-list-group-item v-b-toggle.sidebar-6>{{
            menu6
          }}</b-list-group-item>
          <b-list-group-item>{{ menu7 }}</b-list-group-item>
        </b-list-group>
      </b-sidebar>
      <b-sidebar
        id="sidebar-2"
        :title="menu2"
        shadow
        bg-variant="dark"
        text-variant="light"
      >
        <b-list-group class="bg-dark">
          <b-list-group-item
            v-for="(item, index) in sub2"
            :key="index"
            href="#"
            >{{ item.title }}</b-list-group-item
          >
        </b-list-group>
      </b-sidebar>
      <b-sidebar
        id="sidebar-3"
        :title="menu3"
        shadow
        bg-variant="dark"
        text-variant="light"
      >
        <b-list-group class="bg-dark">
          <b-list-group-item
            v-for="(item, index) in sub3"
            :key="index"
            href="#"
            >{{ item.title }}</b-list-group-item
          >
        </b-list-group>
      </b-sidebar>
      <b-sidebar
        id="sidebar-4"
        :title="menu4"
        shadow
        bg-variant="dark"
        text-variant="light"
      >
        <b-list-group class="bg-dark">
          <b-list-group-item
            v-for="(item, index) in sub4"
            :key="index"
            href="#"
            >{{ item.title }}</b-list-group-item
          >
        </b-list-group>
      </b-sidebar>
      <b-sidebar
        id="sidebar-5"
        :title="menu5"
        shadow
        bg-variant="dark"
        text-variant="light"
      >
        <b-list-group class="bg-dark">
          <b-list-group-item
            v-for="(item, index) in sub5"
            :key="index"
            href="#"
            >{{ item.title }}</b-list-group-item
          >
        </b-list-group>
      </b-sidebar>
      <b-sidebar
        id="sidebar-6"
        :title="menu6"
        shadow
        bg-variant="dark"
        text-variant="light"
      >
        <b-list-group class="bg-dark">
          <b-list-group-item
            v-for="(item, index) in sub6"
            :key="index"
            href="#"
            >{{ item.title }}</b-list-group-item
          >
        </b-list-group>
      </b-sidebar>
    </div>
    <div class="row">
      <div class="col-12 social bg-info text-left">
        <img src="~/assets/facebook.png" alt="facebook" width="20" />
        <img src="~/assets/twitter.png" alt="twitter" width="20" />
        <img src="~/assets/youtube.png" alt="youtube" width="20" />
      </div>
    </div>
    <nav class="navbar navbar-expand-lg navbar-light bg-white">
      <router-link to="/">
        <a class="navbar-brand img-fluid">
          <img src="~/assets/logo.png" alt="logo" class="img-fluid logo" />
        </a>
      </router-link>

      <b-navbar-toggle v-b-toggle.sidebar-1 target=""></b-navbar-toggle>

      <b-collapse is-nav>
        <b-navbar-nav class="ml-auto mr-auto border-success">
          <b-nav-item href="#" class="borderless small font-weight-bold">{{
            menu1
          }}</b-nav-item>
          <b-nav-item-dropdown
            :text="menu2"
            class="borderless small font-weight-bold"
            lazy
          >
            <b-dropdown-item
              v-for="(item, index) in sub2"
              :key="index"
              href="#"
              >{{ item.title }}</b-dropdown-item
            >
          </b-nav-item-dropdown>
          <b-nav-item-dropdown
            class="borderless small font-weight-bold"
            :text="menu3"
          >
            <b-dropdown-item
              v-for="(item, index) in sub3"
              :key="index"
              href="#"
              >{{ item.title }}</b-dropdown-item
            >
          </b-nav-item-dropdown>
          <b-nav-item-dropdown
            class="borderless small font-weight-bold"
            :text="menu4"
          >
            <b-dropdown-item
              v-for="(item, index) in sub4"
              :key="index"
              href="#"
              >{{ item.title }}</b-dropdown-item
            >
          </b-nav-item-dropdown>
          <b-nav-item-dropdown
            class="borderless small font-weight-bold"
            :text="menu5"
          >
            <b-dropdown-item
              v-for="(item, index) in sub5"
              :key="index"
              href="#"
              >{{ item.title }}</b-dropdown-item
            >
          </b-nav-item-dropdown>
          <b-nav-item-dropdown
            class="borderless small font-weight-bold"
            :text="menu6"
          >
            <b-dropdown-item
              v-for="(item, index) in sub6"
              :key="index"
              href="#"
              >{{ item.title }}</b-dropdown-item
            >
          </b-nav-item-dropdown>
          <b-nav-item class="borderless small font-weight-bold" href="#">{{
            menu7
          }}</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </nav>
    <div class="row socialBottom">
      <div class="col-12 socialBottom bg-success"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menu: 'Menu',
      menu1: 'Acceuil',
      menu2: 'A propos de nous',
      menu3: 'Publications',
      menu4: 'Direction 1',
      menu5: 'Direction 2',
      menu6: 'Direction 3',
      menu7: 'A propos de nous',
      sub2: [
        { title: 'Presentation', router: '' },
        { title: 'Mot du president', router: '' },
        { title: 'Organisation', router: '' },
        { title: 'Politique de supervision', router: '' },
        { title: 'Politique de formation', router: '' },
      ],
      sub3: [
        { title: 'Textes legislatifs (lois, decrets, arettés)', router: '' },
        {
          title: 'Textes reglementaires (Réglementation aérotique de Djibouti)',
          router: '',
        },
      ],
      sub4: [
        { title: 'Service 1', router: '' },
        {
          title: 'Service 2',
          router: '',
        },
        {
          title: 'Service 3',
          router: '',
        },
        {
          title: 'Service 4',
          router: '',
        },
      ],
      sub5: [
        { title: 'Service 1', router: '' },
        {
          title: 'Service 2',
          router: '',
        },
        {
          title: 'Service 3',
          router: '',
        },
        {
          title: 'Service 4',
          router: '',
        },
      ],
      sub6: [
        { title: 'Service 1', router: '' },
        {
          title: 'Service 2',
          router: '',
        },
        {
          title: 'Service 3',
          router: '',
        },
        {
          title: 'Service 4',
          router: '',
        },
      ],
    }
  },
}
</script>
<style lang="css" scoped>
.socialBottom {
  min-height: 5px;
}
.navbar {
  width: 100%;
}
@media (min-width: 770px) {
  .logo {
    width: 100px;
  }
}
@media (max-width: 769px) {
  .logo {
    width: 100px;
  }
}
#sidebar-2 {
  transition-duration: 2s;
}
</style>
