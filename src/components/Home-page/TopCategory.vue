<template>
  <div class="top-category">
    <div class="cyber-banner">
      <img src="../../assets/images/cyber-banner.webp" alt="" class="w-100" />
    </div>
    <div class="category">
      <div
        class="d-flex justify-space-between align-center mt-5 mr-10 ml-10 mb-3"
      >
        <h3 style="font-weight: 900; font-size: 25px; color: red">
          Top Categories
        </h3>
        <a href="#" style="color: black">Shop All</a>
      </div>
      <v-container>
        <v-row>
          <v-col cols="2" v-for="cat in categories" :key="cat.title">
            <v-card class="text-center" elevation="0">
              <v-hover v-slot="{ isHovering, props }">
                <div
                  class="img-parent"
                  style="height: 170px; width: 100%; overflow: hidden"
                >
                  <img
                    :src="cat.image"
                    alt=""
                    :style="
                      ' height: 170px; width: 100%; transition: 0.5s all ease-in-out; scale:' +
                      (isHovering ? 1.05 : 1) +
                      ' ; cursor: pointer;'
                    "
                    v-bind="props"
                  />
                </div>
              </v-hover>
              <v-card-text>{{ cat.title }}</v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    categories: [
      {
        title: "Mobile Phones",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/mobile-phones.png?v=10616357514144629263",
      },
      {
        title: " Labtops",
        image:
          " https://new-ella-demo.myshopify.com/cdn/shop/files/laptops-tablets.png?v=17546078654541140209",
      },
      {
        title: " TVS",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/televisions.png?v=792225267698738137",
      },
      {
        title: " Smart Homes",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/smart-homes.png?v=11511407578445752828",
      },
      {
        title: "PCs",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/pcs-accessories.png?v=7913320403362682840",
      },
      {
        title: "Audio & Video",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/audio-video.png?v=17118273463527967791",
      },
      {
        title: "Gaming",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/gaming-accessories.png?v=5365032838061682635",
      },
      {
        title: " Home Appliances",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/home-appliances.png?v=4122646624966862882",
      },
      {
        title: "Kitchen",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/kitchen-appliances.png?v=912885117927234410",
      },
      {
        title: "Cameras",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/cameras.png?v=10468174360605840515",
      },
      {
        title: " Consumables",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/consumables.png?v=1604898607781595964",
      },
      {
        title: " Accessories",
        image:
          "https://new-ella-demo.myshopify.com/cdn/shop/files/accessories.png?v=16090558546215869367",
      },
    ],
  }),
};
</script>
