
<style lang="sass">
$btn-padding-y-lg: 12px
$btn-padding-x-lg: 20px
$body-bg: #74f9ff
$primary: #b2ebed
$secondary: #74f9ff

@import "../node_modules/bootstrap/dist/css/bootstrap.min.css"
@import "../node_modules/bootstrap-icons/font/bootstrap-icons.css"
@import "../node_modules/bootstrap/scss/bootstrap.scss"
</style>

<style >
.btn-width {
  width: 60px;
  height: 50px;
}
.btn-width-special {
  width: 60px;
  height: 120px;
}
/* .btn-width-special2{
  width : 110px;
  height : 50px;
} */
</style>

<template >
  <div class="">
    <!-- <NavBarForcal /> -->
  </div>

  <div
    class="container shadow-lg border rounded-4 display-3 p-3 text-center"
    :style="{ background: activeColor }"
  >
    <div class="row mx-1 mt-1 mb-5 rounded-4">
      <div class="w-full text-primary" :style="{ height: boxHeight }">
        {{ showboxText }}
      </div>
    </div>
    <div
      class="row d-flex justify-content-center align-items-center text-center"
    >
      <div class="col">
        <div class="row">
          <div class="col-3 pb-4 d-flex">
            <button
              @click="ACclearMethod()"
              class="btn btn-width btn-lg btn-secondary p-1"
            >
              AC
            </button>
          </div>
          <div class="col-3 pb-4 d-flex">
            <button
              @click="BackSpaceMethod()"
              class="btn btn-width btn-lg btn-secondary p-1"
            >
              <i class="bi bi-backspace-fill"></i>
            </button>
          </div>
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick('%')"
              class="btn btn-width btn-lg btn-secondary p-1"
            >
              %
            </button>
          </div>
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick('+')"
              class="btn btn-width btn-lg btn-secondary p-1"
            >
              +
            </button>
          </div>
        </div>
        <div class="row">
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick(7)"
              class="btn btn-width btn-lg btn-primary"
            >
              7
            </button>
          </div>
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick(8)"
              class="btn btn-width btn-lg btn-primary"
            >
              8
            </button>
          </div>
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick(9)"
              class="btn btn-width btn-lg btn-primary"
            >
              9
            </button>
          </div>
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick('-')"
              class="btn btn-width btn-lg btn-secondary p-1"
            >
              -
            </button>
          </div>
        </div>
        <div class="row">
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick(4)"
              class="btn btn-width btn-lg btn-primary"
            >
              4
            </button>
          </div>
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick(5)"
              class="btn btn-width btn-lg btn-primary"
            >
              5
            </button>
          </div>
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick(6)"
              class="btn btn-width btn-lg btn-primary"
            >
              6
            </button>
          </div>
          <div class="col-3 pb-4 d-flex">
            <button
              @click="buttonclick('/')"
              class="btn btn-width btn-lg btn-secondary p-1"
            >
              ÷
            </button>
          </div>
        </div>
        <div class="row">
          <div class="col-9">
            <div class="row">
              <div class="col-4 pb-4 d-flex">
                <button
                  @click="buttonclick(1)"
                  class="btn btn-width btn-lg btn-primary"
                >
                  1
                </button>
              </div>
              <div class="col-4 pb-4 d-flex">
                <button
                  @click="buttonclick(2)"
                  class="btn btn-width btn-lg btn-primary"
                >
                  2
                </button>
              </div>
              <div class="col-4 pb-4 d-flex">
                <button
                  @click="buttonclick(3)"
                  class="btn btn-width btn-lg btn-primary"
                >
                  3
                </button>
              </div>
            </div>

            <div class="row">
              <div class="col-4 pb-4 d-flex justify-content-center">
                <button
                  class="btn btn-width btn-lg btn-primary text-center fs-6 ps-2"
                >
                  mode
                </button>
              </div>

              <div class="col-4 pb-4 d-flex justify-content-center">
                <button
                  @click="buttonclick(0)"
                  class="btn btn-width btn-lg btn-primary"
                >
                  0
                </button>
              </div>
              <div class="col-4 pb-4 d-flex justify-content-center">
                <button
                  @click="buttonclick('.')"
                  class="btn btn-width btn-lg btn-primary"
                >
                  .
                </button>
              </div>
            </div>
          </div>

          <div class="col-3 align-items-center">
            <button
              @click="EqualToMethod()"
              class="btn btn-width-special btn-lg btn-secondary p-1"
            >
              =
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import NavBarForcal from './components/NavBarForcal.vue';
export default {
  // components: { NavBarForcal },
  data() {
    return {
      activeColor: "black",

      boxHeight: "150px",
      showboxText: "",
    };
  },
  methods: {
    buttonclick(item) {
      console.log(item);
      this.showboxText += item;
    },
    ACclearMethod() {
      this.showboxText = "";
    },
    EqualToMethod() {
      this.showboxText = eval(this.showboxText);
    },
    BackSpaceMethod() {
      this.showboxText = this.showboxText.slice(0, -1);
    },
  },
};
</script>
