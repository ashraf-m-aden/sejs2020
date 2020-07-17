<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-12 col-md-8 text-left">
        <h4>{{ region.name }}</h4>
        <p>
          <em>{{ region.description }}</em>
        </p>
      </div>
      <div class="col-sm-12 col-md-4">
        <img :src="region.map" alt usemap="#regionMap" />
        <map id="map" name="regionMap">
          <area
            v-for="(ville, index) in cdc"
            :key="index"
            href="#"
            shape="circle"
            :coords="ville.coord"
            :alt="ville.name"
            class="area"
            @click="changeTown(ville.id)"
          />
        </map>
      </div>
    </div>
    <div class="row">
      <div class="col-12 d-flex">
        <div class="normalScreen">
          <v-navigation-drawer width="auto" height="auto" permanent>
            <div class="d-flex justify-content-around">
              <span class="md-title">{{ choosenCDC.name }}</span>
            </div>

            <v-divider></v-divider>

            <v-list>
              <v-list-item
                v-for="(item, index) in subject"
                :key="index"
                @click="changeSubject(index)"
              >
                <v-list-item-icon>
                  <v-icon>{{ item.icon }}</v-icon>
                </v-list-item-icon>

                <v-list-item-content>
                  <v-list-item-title>{{ item.subject }}</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-navigation-drawer>
        </div>
        <div class="isMobile">
          <v-navigation-drawer
            v-model="drawer"
            absolute
            temporary
            width="auto"
            height="auto"
          >
            <div class="d-flex justify-content-around">
              <span class="md-title">{{ choosenCDC.name }}</span>
              <button @click.stop="drawer = !drawer">
                <v-icon>mdi-close-circle-outline</v-icon>
              </button>
            </div>

            <v-divider></v-divider>

            <v-list>
              <v-list-item
                v-for="(item, index) in subject"
                :key="index"
                @click="changeSubject(index)"
              >
                <v-list-item-icon>
                  <v-icon>{{ item.icon }}</v-icon>
                </v-list-item-icon>

                <v-list-item-content>
                  <v-list-item-title>{{ item.subject }}</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-navigation-drawer>
        </div>
        <div>
          <div class="d-flex justify-content-between">
            <h5 class="">{{ choosenSubject }}</h5>
            <v-app-bar-nav-icon
              class="isMobile"
              @click.stop="drawer = !drawer"
            ></v-app-bar-nav-icon>
          </div>

          <p class="text-left">
            {{ choosenCDC[choosenSubject] }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'PersistentMini',
  data() {
    return {
      menuVisible: false,
      drawer: false,

      region: [],
      cdc: [
        {
          id: 2,
          name: 'Khor-Angar',
          coord: '243, 126, 14',
          Description:
            'Ici se place la description complete du CDC de Khor-Angar',
          Activités: 'ici les activités',
          Infrastructure: 'ici les infrastructures sont presentés',
          Personel: 'ici le personel',
          Horraires: 'ici les horaires',
          Communiqués: 'ici les communiqués',
        },
        {
          id: 1,
          name: 'Obock',
          coord: '240, 275, 14',
          Description: "Ici se place la description complete du CDC d'Obock",
          Activités: 'ici les activités',
          Infrastructure: 'ici les infrastructures sont presentés',
          Personel: 'ici le personel',
          Horraires: 'ici les horaires',
          Communiqués: 'ici les communiqués',
        },
      ],
      subject: [
        { id: 1, icon: 'mdi-information-outline', subject: 'Description' },
        { id: 2, icon: 'mdi-home-circle-outline', subject: 'Infrastructure' },
        { id: 3, icon: 'mdi-basketball', subject: 'Activités' },
        { id: 4, icon: 'mdi-account-group', subject: 'Personel' },
        { id: 5, icon: 'mdi-calendar-clock', subject: 'Horraires' },
        { id: 6, icon: 'mdi-android-messages', subject: 'Communiqués' },
      ],
      choosenCDC: '',
      choosenSubject: 'Description',
      true: true,
    }
  },
  watch: {
    group() {
      this.drawer = false
    },
  },
  created() {
    const townId = this.$route.query.townId

    axios
      .post('http://localhost:3001/getTown', {
        townId,
      })
      .then((data) => {
        this.region = data.data[0]
      })
      .catch(() => {
        this.$router.push({ path: '/' })
      })
    this.choosenCDC = this.cdc[0]
    this.choosenCDC.subject = 'Description'
  },
  methods: {
    toggleMenu() {
      this.menuVisible = !this.menuVisible
    },
    changeSubject(index) {
      this.choosenSubject = this.subject[index].subject
    },
    changeTown(id) {
      this.cdc.forEach((element) => {
        if (element.id === id) {
          this.choosenCDC = element
        }
      })
    },
  },
  head() {
    return {
      title: 'SEJS | ' + this.region.name,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            'Toutes les informations sur les CDC de la ville de: ' +
            this.region.name,
        },
      ],
    }
  },
}
</script>

<style lang="css" scoped>
.page-container {
  min-height: 300px;
  overflow: hidden;
  position: relative;
  border: 1px solid rgba(#000, 0.12);
}

.md-drawer {
  width: auto;
  max-width: calc(100vw - 125px);
  height: auto;
}

.md-content {
  padding: 16px;
}
.md-app {
  min-height: 350px;
  border: 1px solid rgba(#000, 0.12);
}

@media (min-width: 770px) {
  .isMobile {
    display: none;
  }
}
@media (max-width: 769px) {
  .normalScreen {
    display: none;
  }
}
</style>
