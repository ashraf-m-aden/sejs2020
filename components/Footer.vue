<template>
  <div>
    <div class="row bg-info pt-5 pb-5">
      <div class="col-12 col-md-4 text-light d-flex flex-column">
        <a class="navbar-brand img-fluid mb-2" href="#">
          <img src="~/assets/logo1.png" alt="logo" class="img-fluid logo" />
        </a>
        <span
          >Regulation and oversight of Aviation Safety & Security; Economic
          regulation of Air Services and development of Civil Aviation;
          Provision of Air Navigation Services, and Training of Aviation
          personnel KCAA</span
        >
      </div>
      <div class="col-12 col-md-4 text-light">
        <h4>Siège sociale</h4>
        Aviation House, Jomo Kenyatta International <br />
        Airport, P.O. Box 30163 -00100 Nairobi, <br />
        <font-awesome-icon :icon="['fas', 'phone']" />
        +254 020 6827470-5 <br />
        <font-awesome-icon :icon="['fas', 'phone']" />

        +254 728 606 570, <br />
        <font-awesome-icon :icon="['fas', 'phone']" />

        +254 709 725000, <br />
        <font-awesome-icon :icon="['fas', 'phone']" />

        +254 728 606 586, <br />
        <font-awesome-icon :icon="['fas', 'mobile']" />

        +254 734 000 491,<br />

        <font-awesome-icon :icon="['fas', 'envelope']" />

        info@kcaa.or.ke
      </div>
      <div class="col-12 col-md-4 text-light">
        <h4>Liens rapide</h4>
        Presidence <br />
        La nation <br />
        Air Djibouti <br />
        e.gove <br />
      </div>
    </div>
    <div class="row bg-success">
      <div class="col-12 text-center medium text-light pb-3">
        Copyright © 2020 Djibouti Civil Aviation Authority. All Rights Reserved
      </div>
    </div>
  </div>
</template>

<style lang="css" scoped>
@media (min-width: 770px) {
  .logo {
    width: 200px;
  }
}
@media (max-width: 769px) {
  .logo {
    width: 100px;
  }
}
</style>
