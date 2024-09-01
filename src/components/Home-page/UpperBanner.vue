<template>
  <div class="banner">
    <div class="parent">
      <v-container>
        <v-row>
          <v-col cols="6">
            <div class="cont">
              <h3><span>Huge Saving</span> on UHD Televisions</h3>
              <p class="hint">Sale up to 70% off on selected items*</p>
              <!-- <v-btn density="compact" variant="outlined" class="sign-btn py-3 px-10"> -->
              <v-btn variant="outlined" class="sign-btn"> Shop Now</v-btn>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </div>
</template>
<style lang="scss">
.banner {
  .parent {
    height: 390px;
    background-image: url(../../assets/images/banner-bg.jpg);
    background-size: cover;
    background-position: left top;

    .cont {
      color: white;
      padding: 40px 0 0 100px;

      h3 {
        font-size: 45px;
        font-weight: 900;

        span {
          color: rgb(33, 236, 33);
        }
      }

      p {
        margin: 20px 0;
      }

      .sign-btn {
        border-radius: 30px;
        text-transform: none;
        padding-top: 10px;
        padding-bottom: 30px;
        padding-right: 50px;
        padding-left: 50px;
      }
    }
  }
}
</style>
