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
        <div class="absolute-bottom custom-caption">
          <div class="text-h3">25% Descuento</div>
          <div class="text-subtitle1">En celulares</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="second" img-src="https://www.lavanguardia.com/r/GODO/LV/p6/Internacional/2019/11/30/Recortada/img_slozano_20191130-012040_imagenes_lv_otras_fuentes_istock-501649409-kK4-U471954307028VPI-992x558@LaVanguardia-Web.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h3">Servicio de sicario</div>
          <div class="text-subtitle1">Suegras 25% OFF</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="third" img-src="http://www.doomsdaynews.com/wp-content/uploads/2014/06/community-people.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h3">Venta de Personas</div>
          <div class="text-subtitle1">Elegila del color y edad que quieras</div>
        </div>
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
            <q-tab name="nuevos" label="Nuevo productos"></q-tab>
            <q-tab name="promos" label="Promociones"></q-tab>
          </q-tabs>

          <q-separator ></q-separator>

          <q-tab-panels v-model="tab" animated>
            <q-tab-panel name="nuevos">
              <div class="text-h6"></div>
              <div class="row fit justify-start q-gutter-xs q-col-gutter no-wrap">
                <Product v-for="pr in products" :key="pr.id" v-bind="pr"/>
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
    <div class="text-grey-9 text-weight-bold">
      <div class="row items-center q-mx-sm">
        <div class="col-lg-12 col-md-12 col-sm-12 col-xs-12 q-mt-sm">
          <div class="q-pl-md bg-white q-pt-sm">
            <span class="text-grey-9 text-h6 text-weight-bold">Trending in</span> <a
            class="text-primary q-ml-sm cursor-pointer">[see more]</a>
          </div>
          <q-carousel
            v-model="trending_slide"
            transition-prev="slide-right"
            transition-next="slide-left"
            swipeable
            animated
            control-color="primary"
            navigation
            padding
            arrows
            height="260px"
            class="rounded-borders"
          >
            <q-carousel-slide v-for="val in [1,2,3]" :name="val" v-bind:key="val" class="column no-wrap">
              <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
                <q-img @click="$router.push('/category')" style="border:1px solid lightgrey;" class="rounded-borders col-lg-3 col-md-3 col-sm-12 col-xs-12 cursor-pointer full-height"
                       src="https://www.graphicsprings.com/filestorage/stencils/1cdf3eae16b6d0da3f16ff12f7650a24.png">
                  <div class="absolute-bottom custom-caption" style="background-color:rgba(0, 0, 0, .5);">
                    <div class="text-caption text-weight-bolder">Electronics</div>
                  </div>
                </q-img>
                <q-img @click="$router.push('/category')" style="border:1px solid lightgrey;" class="rounded-borders col-lg-3 col-md-3 col-sm-12 col-xs-12 cursor-pointer full-height"
                       src="https://www.graphicsprings.com/filestorage/stencils/d3dd5cb632e0826d9e6136af3241b28e.png">
                  <div class="absolute-bottom custom-caption" style="background-color:rgba(0, 0, 0, .5);">
                    <div class="text-caption text-weight-bolder">TVs and Appliances</div>
                  </div>
                </q-img>
                <q-img @click="$router.push('/category')" style="border:1px solid lightgrey;" class="rounded-borders col-lg-3 col-md-3 col-sm-12 col-xs-12 cursor-pointer full-height"
                       src="https://www.graphicsprings.com/filestorage/stencils/1cdf3eae16b6d0da3f16ff12f7650a24.png">
                  <div class="absolute-bottom custom-caption" style="background-color:rgba(0, 0, 0, .5);">
                    <div class="text-caption text-weight-bolder">Men</div>
                  </div>
                </q-img>
                <q-img @click="$router.push('/category')" style="border:1px solid lightgrey;" class="rounded-borders col-lg-3 col-md-3 col-sm-12 col-xs-12 cursor-pointer full-height"
                       src="https://www.graphicsprings.com/filestorage/stencils/d3dd5cb632e0826d9e6136af3241b28e.png">
                  <div class="absolute-bottom custom-caption" style="background-color:rgba(0, 0, 0, .5);">
                    <div class="text-caption text-weight-bolder">Women</div>
                  </div>
                </q-img>
              </div>
            </q-carousel-slide>
          </q-carousel>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import Product from 'components/Product.vue'

export default {
  name: 'home',
  components: {
    Product
  },
  computed: {
  },
  data () {
    return {
      tab: 'nuevos',
      slide: 'first',
      trending_slide: 1,
      latest_slide: 1,
      products: [
        {
          id: 1,
          name: 'Huawei P300',
          img: 'https://img.ibxk.com.br/2018/03/20/20111040166049.jpg',
          desc: 'Nuevo celu, sin usar',
          precio: 1000,
          precOriginal: 1260
        },
        {
          id: 2,
          name: 'Mano de Peron',
          img: 'https://historiasdeterror10.com/wp-content/uploads/2019/03/cosaaddams.jpg',
          desc: 'Mano original del gran y unico gral Peron',
          precio: 25000,
          precOriginal: 27000
        },
        {
          id: 3,
          name: 'Caja Misteriosa',
          img: 'https://www.historias-de-terror.org/wp-content/uploads/2019/01/caja-misteriosa-de-la-deep-web-D_NQ_NP_873705-MCO27972793910_082018-F.jpg',
          desc: 'Para regalar a tus hijos, caja super misteriosa sorpresa',
          precio: 3000,
          precOriginal: 3200
        },
        {
          id: 4,
          name: 'Hackers a Domicilio',
          img: 'https://as01.epimg.net/meristation/imagenes/2020/05/22/betech/1590184541_747225_1590184613_noticia_normal.jpg',
          desc: 'Los mejores hackers a domicilio',
          precio: 3000,
          precOriginal: 3200
        },
        {
          id: 5,
          name: 'Exportaciones',
          img: 'https://previews.123rf.com/images/alekseyk1975/alekseyk19751607/alekseyk1975160700055/60482488-planeador-planeador-ilustraci%C3%B3n-aislado-en-el-fondo-del-cielo.jpg',
          desc: 'Exportacion de materiales y capital humano',
          precio: 500000,
          precOriginal: 500350
        },
        {
          id: 6,
          name: 'Disfraces',
          img: 'https://scontent.faep4-1.fna.fbcdn.net/v/t31.0-8/11168766_952822374769959_1141325939721031220_o.jpg?_nc_cat=103&_nc_sid=9267fe&_nc_ohc=QYmkqE0ttFEAX_aZAlT&_nc_ht=scontent.faep4-1.fna&oh=8acabc487407629324e481d0e0e35a9f&oe=5F1BB674',
          desc: 'Alquiler de disfraces para fiestas',
          precio: 3250,
          precOriginal: 3250
        }
      ]
    }
  },
  methods: {}
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
