<template>
  <q-page class="q-mt-sm">
    <div class="q-pl-md bg-white q-pt-sm">
      <div class="row">
        <div v-for="pr in productos" :key="pr.id" class="col-3 q-mt-lg">
            <Product :v-show="pr.idCategoria == [($route.params.id)]" v-bind="pr"/>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import Product from 'components/Product.vue'
import router from '../router'
import listaProductos from '../listaProductos'

export default {
  name: 'details',
  components: {
    Product
  },
  computed: {
  },
  methods: {
    navigate () {
      router.go(-1)
    }
  },
  created () {
    this.idLocal = this.$route.params.id
  },
  data () {
    return {
      tab: 'nuevos',
      slide: 'first',
      trending_slide: 1,
      latest_slide: 1,
      idLocal: 0,
      productos: listaProductos
    }
  }
}
</script>
