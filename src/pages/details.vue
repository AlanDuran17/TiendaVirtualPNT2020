<template>
  <q-page class="q-mt-sm">
    <div class="row" v-bind="prod = productos[($route.params.id)-1]">
      <div class="col-4">
        <div id="cajaProducto" class="q-pa-md">
          <q-img id="imagenProducto" style="" class="rounded-borders" :src="prod.img" width=100% height=auto />
        </div>
      </div>
      <div class="col">
          <div id="cajaProducto" class="q-mt-md">
          <div id="nombreProducto" class="text-weight-bold text-h5">{{prod.name}}</div>
          <div id="descripcionProducto" class="text-h6 text-grey">{{prod.desc}}</div>
          <div>
            <span id="precioPro" class="text-h4 text-weight-light text-green-6">${{prod.precio}}</span><span id="precioPro" class="q-ml-sm text-h4 text-weight-light text-grey-6" style="text-decoration: line-through">${{prod.precOriginal}}</span>
          </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import router from '../router'
import listaProductos from '../listaProductos'

export default {
  name: 'details',
  components: {
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

<style scoped>
  .custom-caption {
    text-align: center;
    padding: 8px;
    color: white;
    background-color: rgba(0, 0, 0, .3);
  }
  #imagenProducto{
    width: 500px;
    height: 450px;
  }

</style>
