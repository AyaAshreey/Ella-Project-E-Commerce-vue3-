<template>
  <div
    class="top-offers pb-16 pt-9"
    style="background-color: rgba(128, 128, 128, 0.13)"
  >
    <v-container fluid>
      <v-row>
        <v-col cols="4 py-0 pr-6">
          <v-hover v-slot="{ isHovering, props }">
            <div
              class="parent"
              v-bind="props"
              style="overflow: hidden; border-radius: 7px"
            >
              <img
                src="../../assets/images/playstations.webp"
                alt=""
                :style="`width: 100 % ; height: 100%; cursor:pointer; transition: 0.5s all ease-in-out;  scale: ${
                  isHovering ? 1.1 : 1
                }`"
              />
            </div>
          </v-hover>
        </v-col>
        <v-col cols="4 py-0 pr-6">
          <v-hover v-slot="{ isHovering, props }">
            <div
              class="parent"
              v-bind="props"
              style="overflow: hidden; border-radius: 7px"
            >
              <img
                src="../../assets/images/headset.webp"
                alt=""
                :style="`width: 100 % ; height: 100%; cursor:pointer; transition: 0.5s all ease-in-out; scale: ${
                  isHovering ? 1.1 : 1
                }`"
              />
            </div>
          </v-hover>
        </v-col>
        <v-col cols="4 py-0 pr-6">
          <v-hover v-slot="{ isHovering, props }">
            <div
              class="parent"
              v-bind="props"
              style="overflow: hidden; border-radius: 7px"
            >
              <img
                src="../../assets/images/chairs.webp"
                alt=""
                :style="`width: 100 % ; height: 100%; cursor:pointer; transition: 0.5s all ease-in-out; scale: ${
                  isHovering ? 1.1 : 1
                }`"
              />
            </div>
          </v-hover>
        </v-col>
      </v-row>
      <!-- =========================================== -->
      <v-row class="mt-9">
        <v-col cols="6" class="mt-2 pr-5 py-0">
          <v-hover v-slot="{ isHovering, props }">
            <div class="parent pr-2" v-bind="props" style="overflow: hidden">
              <img
                src="../../assets/images/iphones.webp"
                alt=""
                :style="`width: 100 % ; height: 100% cursor:pointer; transition: 0.5s all ease-in-out;  scale: ${
                  isHovering ? 1.1 : 1
                }`"
              />
            </div>
          </v-hover>
        </v-col>
        <v-col cols="6" class="mt-2 pl-5 py-0">
          <v-hover v-slot="{ isHovering, props }">
            <div class="parent pl-2" v-bind="props" style="overflow: hidden">
              <img
                src="../../assets/images/laptops.webp"
                alt=""
                :style="`width: 100 % ; height: 100% cursor:pointer; transition: 0.5s all ease-in-out;  scale: ${
                  isHovering ? 1.1 : 1
                }`"
              />
            </div>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
