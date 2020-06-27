<template>
    <div @click="$router.push('/details')" id="cajaProducto" class="col-lg-2 col-md-2 col-sm-12 col-xs-12 hover_border_grey text-center full-height">
        <q-img style="" class="rounded-borders" :src="img" width=200px height=150px>
        </q-img>
        <div class="text-weight-bold text-subtitle1">{{name}}</div>
        <div id="descripcionProducto" class="text-caption text-overline text-grey">{{desc}}</div>
        <div><span class="q-ml-sm text-green-6">{{precio}}$</span><span class="q-ml-sm text-grey-6" style="text-decoration: line-through">{{precOriginal}}$</span></div>
    </div>
</template>

<script>
export default {
  name: 'Product',
  props: {
    id: {
      type: Number,
      required: true
    },

    name: {
      type: String,
      default: ''
    },

    img: {
      type: String,
      default: '#'
    },

    desc: {
      type: String,
      default: 'un Producto'
    },

    precio: {
      type: Number,
      default: 0
    },

    precOriginal: {
      type: Number,
      default: 0
    }
  }
}
</script>
