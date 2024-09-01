<template>
  <div class="drawer">
    <v-navigation-drawer v-model="drawer" temporary location="right">
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Unde
        asperiores accusamus aspernatur obcaecati velit maxime, illum
        exercitationem vitae et pariatur ratione reiciendis consequuntur nemo
        itaque aperiam minus laboriosam dolorem dicta?
      </p>
    </v-navigation-drawer>
  </div>
</template>
<script>
export default {
  inject: ["Emitter"],
  data: () => ({
    drawer: false,
  }),
  mounted() {
    this.Emitter.on("openCart", () => {
      this.drawer = true;
    });
  },
};
</script>
