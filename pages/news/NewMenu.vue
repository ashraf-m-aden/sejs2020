<template>
  <div class="row">
    <div class="col-12 text-center">
      <h4 class="card-header bg-info text-light mb-5">
        Derniers articles
      </h4>
      <b-container>
        <b-row>
          <b-col
            v-for="(item, index) in paginatedItems"
            :key="index"
            cols="12"
            sm="4"
            class="my-1"
          >
            <b-card
              :bg-variant="item.variant"
              :header="item.title"
              class="text-center"
            >
              <p class="card-text">{{ item.content }}</p>
            </b-card>
          </b-col>
        </b-row>

        <b-row>
          <b-col md="6" class="my-1">
            <b-pagination
              v-model="currentPage"
              :total-rows="totalRows"
              :per-page="perPage"
              class="my-0"
              @change="onPageChanged"
            />
          </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
const items = [
  {
    title: 'Primary',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
    variant: 'primary',
  },
  {
    title: 'Secondary',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
    variant: 'secondary',
  },
  {
    title: 'Success',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
    variant: 'success',
  },
  {
    title: 'Info',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
    variant: 'info',
  },
  {
    title: 'Warning',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
    variant: 'warning',
  },
  {
    title: 'Danger',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
    variant: 'danger',
  },
]
export default {
  data() {
    return {
      currentPage: 1,
      paginatedItems: this.news,
      perPage: 2,
      totalRows: items.length,
      news: [
        {
          img: '~/assets/new1.jpg',
          title: 'Card title',
          content:
            'This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.',
          date: 'Last updated 3 mins ago',
        },
        {
          img: '~/assets/new1.jpg',
          title: 'Card title',
          content:
            'This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.',
          date: 'Last updated 3 mins ago',
        },
        {
          img: '~/assets/new1.jpg',
          title: 'Card title',
          content:
            'This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.',
          date: 'Last updated 3 mins ago',
        },
        {
          img: '~/assets/new1.jpg',
          title: 'Card title',
          content:
            'This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.',
          date: 'Last updated 3 mins ago',
        },
        {
          img: '~/assets/new1.jpg',
          title: 'Card title',
          content:
            'This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.',
          date: 'Last updated 3 mins ago',
        },
      ],
      items: this.news,
    }
  },
  computed: {
    rows() {
      return this.news.length
    },
  },
  mounted() {
    this.paginate(this.perPage, 0)
  },
  methods: {
    paginate(pageSize, pageNumber) {
      const itemsToParse = this.news
      this.paginatedItems = itemsToParse.slice(
        pageNumber * pageSize,
        (pageNumber + 1) * pageSize
      )
    },
    onPageChanged(page) {
      this.paginate(this.perPage, page - 1)
    },
  },
}
</script>
