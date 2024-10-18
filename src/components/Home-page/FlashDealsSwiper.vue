<template>
  <div class="products-swiper py-16">
    <div class="titl d-flex justify-space-between align-center mb-10">
      <h3
        style="
          font-weight: 900;
          color: red;
          padding-left: 20px;
          font-size: 30px;
        "
      >
        Flash Sale
      </h3>
      <a href="#" style="padding-right: 25px; color: black">Shop All</a>
    </div>
    <Swiper
      class="pb-9 px-5"
      :pagination="{ el: '.swiper-pagination', clickable: true }"
      :modules="modules"
      :slides-per-view="4"
      :space-between="35"
      :navigation="{ prevIcon: '.swiper-prev', nextIcon: '.swiper-next' }"
      :autoplay="{
        delay: 2000,
        pauseOnMouseEnter: true,
        disableOnInteraction: false,
      }"
      :loop="true"
    >
      <swiper-slide v-for="item in products" :key="item.id">
        <v-card elevation="0" class="pb-5">
          <v-hover v-slot="{ isHovering, props }">
            <div class="img-parent" style="height: 200px; overflow: hidden">
              <img
                :src="
                  showenItem[item.title]
                    ? showenItem[item.title]
                    : item.thumbnail
                "
                alt=""
                class="w-100"
                :style="
                  'height: 200px; transition: 0.5s all ease-in-out; scale:' +
                  (isHovering ? 1.05 : 1) +
                  ' ; cursor: pointer;'
                "
                v-bind="props"
              />
            </div>
          </v-hover>
          <v-card-text class="pl-0 pb-1">
            ({{ item.title }})
            {{
              `( ${item.titl}) (${item.description})`.length <= 57
                ? `( ${item.titl}) (${item.description})`
                : `(
              ${item.titl}) (${item.description})`.substring(0, 57) + "..."
            }}
          </v-card-text>

          <v-rating
            v-model="item.rating"
            half-increments
            readonly
            color="yellow-darken-2"
            density="compact"
            size="x-small"
          >
          </v-rating>
          <v-card-text class="pl-0 pt-0">
            <del> ${{ item.price }}</del> From
            <span class="text-red" style="font-weight: 900; font-size: 16px">
              ${{
                Math.ceil(
                  item.price - item.price * (item.discountPercentage / 100)
                )
              }}
            </span>
          </v-card-text>

          <v-btn-toggle v-model="showenItem[item.title]" mandatory>
            <v-btn
              v-for="(pic, i) in item.images"
              :value="pic"
              :key="i"
              size="x-small"
              rounded="xl"
            >
              <img
                :src="pic"
                width="30"
                height="30"
                style="border-radius: 50%; border: 1px solid gray"
                alt=""
              />
            </v-btn>
          </v-btn-toggle>
          <div class="mt-5">
            <v-btn
              density="compact"
              class="py-2 px-12"
              style="text-transform: none"
              rounded
              variant="outlined"
            >
              Choose OPtions
            </v-btn>
          </div>
        </v-card>
      </swiper-slide>
      <div class="swiper-prev"></div>
      <div class="swiper-next"></div>

      <div class="swiper-pagination"></div>
    </Swiper>
    <!-- <v-container fluid>
              <v-row>
                  <v-col cols="3" v-for="item in products" :key="item.id">
                      <v-card elevation="0" class="pb-5">
                          <img :src="showenItem[item.title] ? showenItem[item.title] : item.thumbnail" alt=""
                              class="w-100" style="height: 200px;">
                          <v-card-text class="pl-0 pb-1">
                              ({{ item.title }})
                              {{ item.description.split(" ").length <= 8 ? item.description : item.description.
                  split(" ").slice(0, 8).join(" ") + " ..." }} </v-card-text>
  
                                  <v-rating v-model="item.rating" half-increments readonly color="yellow-darken-2"
                                      density="compact" size="x-small">
  
                                  </v-rating>
                                  <v-card-text class="pl-0 pt-0">
                                      <del> ${{ item.price }}</del> From
                                      <span class=" text-red" style="font-weight: 900; font-size: 16px;">
                                          ${{ Math.ceil(item.price - item.price * (item.discountPercentage / 100)) }}
                                      </span>
                                  </v-card-text>
  
                                  <v-btn-toggle v-model="showenItem[item.title]">
                                      <v-btn v-for="(pic, i) in item.images" :value="pic" :key="i" size="x-small">
                                          <img :src="pic" width="30" height="30"
                                              style="border-radius: 50%; border: 1px solid gray;" alt="">
                                      </v-btn>
                                  </v-btn-toggle>
                                  <div class="mt-5">
                                      <v-btn density="compact" class="py-2 px-12" style="text-transform: none;" rounded
                                          variant="outlined">
                                          Choose OPtions
                                      </v-btn>
                                  </div>
                      </v-card>
                  </v-col>
              </v-row>
          </v-container> -->
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import { Pagination, Navigation, Autoplay } from "swiper";

export default {
  props: {
    products: {
      type: Array,
    },
  },
  setup() {
    return {
      modules: [Pagination, Navigation, Autoplay],
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  data: () => ({
    showenItem: {},
  }),
};
</script>
<style lang="scss">
.products-swiper {
  .swiper-button-next,
  .swiper-button-prev {
    border: 2px solid rgb(71, 70, 70);
    border-radius: 50%;
    width: 25px;
    height: 25px;
    background-color: white;
    top: 40%;

    &::after {
      font-size: 12px;
      color: rgb(71, 70, 70);
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }
}
</style>
