<template>
  <q-page class="q-mt-sm">
    <div class="q-pa-md">
    <q-carousel
      arrows
      animated
      v-model="slide"
      height="400px"
      infinite
    >
      <q-carousel-slide name="first" img-src="~assets/carouselsite1.jpg">
      </q-carousel-slide>
      <q-carousel-slide name="second" img-src="https://http2.mlstatic.com/optimize/o:f_webp/resources/deals/exhibitors_resources/mla-home-desktop-slider-picture-5ebcd51d-c856-4036-9239-41c3a805e7c7.jpg">
      </q-carousel-slide>
      <q-carousel-slide name="third" img-src="https://http2.mlstatic.com/optimize/o:f_webp/resources/deals/exhibitors_resources/mla-home-desktop-slider-picture-5d684f3a-4ada-4075-9e37-7f5787ca013d.jpg">
      </q-carousel-slide>
    </q-carousel>
    </div>
    <div class="q-pa-md">
      <div class="q-gutter-y-md" style="">
        <q-card>
          <q-tabs
            v-model="tab"
            dense
            class="text-grey"
            active-color="primary"
            indicator-color="primary"
            align="justify"
            narrow-indicator
          >
            <q-tab name="nuevos" label="Nuevos productos"></q-tab>
            <q-tab name="promos" label="Promociones"></q-tab>
          </q-tabs>

          <q-separator ></q-separator>

          <q-tab-panels v-model="tab" animated>
            <q-tab-panel name="nuevos">
              <div class="text-h6"></div>
              <div class="row">
                <div v-for="pr in products" :key="pr.id" class="col-3 q-mt-lg">
                  <Product v-bind="pr"/>
                </div>
              </div>
            </q-tab-panel>
            <q-tab-panel name="promos">
              <div class="text-h6">Alarms</div>
              Lorem ipsum dolor sit amet consectetur adipisicing elit.
            </q-tab-panel>
          </q-tab-panels>
        </q-card>
      </div>
    </div>
    <div class="text-grey-9 text-weight-bold q-pa-sm">
      <div class="row items-center q-mx-sm">
        <div class="col-lg-12 col-md-12 col-sm-12 col-xs-12 q-mt-sm">
          <div class="q-pl-md bg-white q-pt-sm">
            <span class="text-grey-9 text-h6 text-weight-bold">Categorias</span> <a
            class="text-primary q-ml-sm cursor-pointer">[see more]</a>
          </div>
          <div class="q-pl-md bg-white q-pt-sm">
            <div v-for="cat in categorias" :key="cat.id" class="q-pa-sm inline-block">
              <Categoria v-bind="cat"/>
            </div>
          </div>
        </div>
      </div>
    </div>

  </q-page>
</template>

<script>
import Product from 'components/Product.vue'
import Categoria from 'components/Categoria.vue'
import listaProductos from '../listaProductos.js'
import listaCategorias from '../listaCategorias.js'

export default {
  name: 'home',
  components: {
    Product,
    Categoria
  },
  computed: {
    categoriasGroups () {
      return Array.from(Array(Math.ceil(this.categorias.length / 4)).keys())
    }
  },
  methods: {},
  data () {
    return {
      tab: 'nuevos',
      slide: 'first',
      trending_slide: 1,
      latest_slide: 1,
      products: listaProductos,
      categorias: listaCategorias
    }
  }
}
</script>

<style scoped>
  .custom-caption {
    text-align: center;
    padding: 8px;
    color: white;
    background-color: rgba(0, 0, 0, .3);
  }

</style>
