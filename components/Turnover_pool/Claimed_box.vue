<template>
<div class="box rounded-10 p-2 my-3 d-md-flex">
        <div class="p-3 col">
          <span class="d-none d-md-block ms-2 mb-2">Total claimed</span>
          <div class="d-flex align-items-center">
            <span class="me-4 me-md-1 d-flex">
              <img src="~/assets/images/logo.png" alt="" class="img-1" />
              <img src="~/assets/images/bnb.png" alt="" class="img-2" />
            </span>
            <div class="">
              <span class="d-md-none">Total claimed</span>
              <h2>$586.45k</h2>
            </div>
          </div>
        </div>
        <div class="border"></div>
        <div class="p-3 col">
          <span class="d-none d-md-block ms-2 mb-2"
            >Pending GYMNET rewards</span
          >
          <div class="d-lg-flex align-items-center justify-content-between">
            <div class="d-flex align-items-center">
              <span class="me-4">
                <img src="~/assets/images/logo.png" alt="" class="img-1" />
              </span>
              <div class="">
                <span class="d-md-none">Pending GYMNET rewards</span>

                <h2>768.56</h2>
              </div>
            </div>
            <div class="col col-lg-4">
              <div
                class="btn border-primary text-primary rounded-10 mt-2 mt-lg-0 w-100"
              >
                Calim
              </div>
            </div>
          </div>
        </div>
        <div class="border"></div>
        <div class="p-3 col">
          <span class="d-none d-md-block ms-2 mb-2">Pending BUSD rewards</span>
          <div class="d-lg-flex align-items-center justify-content-between">
            <div class="d-flex align-items-center">
              <span class="me-4">
                <img src="~/assets/images/bnb.png" alt="" class="img-1" />
              </span>
              <div class="">
                <span class="d-md-none">Pending BUSD rewards</span>
                <h2>468.56</h2>
              </div>
            </div>
            <div class="col col-lg-4">
              <div
                class="btn border-primary text-primary rounded-10 mt-2 mt-lg-0 w-100"
              >
                Calim
              </div>
            </div>
          </div>
        </div>
      </div>
</template>

<style lang="scss" scoped>

  .box {
    background: #edf0f4;
    img {
      width: 40px;
    }
    .img-2 {
      margin-left: -15px;
    }
  }

</style>
