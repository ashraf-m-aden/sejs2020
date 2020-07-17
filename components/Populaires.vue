<template>
  <div>
    <h5 class="card-header bg-info text-light mb-5">
      Articles les plus vus
    </h5>
    <div>
      <ul class="list-unstyled">
        <b-media tag="li">
          <template v-slot:aside>
            <b-img src="~/assets/new1.jpg" width="64" alt="placeholder">
            </b-img>
          </template>
          <h5 class="mt-0 mb-1">Titre 1</h5>
          <p class="mb-0">
            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus
            scelerisque ante sollicitudin. Cras purus odio, vestibulum in
            vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi
            vulputate fringilla. Donec lacinia congue felis in faucibus.
          </p>
        </b-media>
        <b-media tag="li">
          <template v-slot:aside>
            <b-img src="~/assets/new1.jpg" width="64" alt="placeholder">
            </b-img>
          </template>
          <h5 class="mt-0 mb-1">Titre 2</h5>
          <p class="mb-0">
            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus
            scelerisque ante sollicitudin. Cras purus odio, vestibulum in
            vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi
            vulputate fringilla. Donec lacinia congue felis in faucibus.
          </p>
        </b-media>
      </ul>
    </div>
  </div>
</template>
