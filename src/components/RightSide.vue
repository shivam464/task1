<template>
  <div class="right_side_wrapper">
    <div class="total_item_wrapper">
      <p>2506 Items</p>
      <div>
        <div class="btn-group">
          <button
            type="button"
            class="btn dropdown-toggle"
            data-toggle="dropdown"
            aria-haspopup="true"
            aria-expanded="false"
          >
            Newest
          </button>
          <div class="dropdown-menu dropdown-menu-right">
            <button class="dropdown-item" type="button">Action</button>
            <button class="dropdown-item" type="button">Another action</button>
            <button class="dropdown-item" type="button">
              Something else here
            </button>
          </div>
        </div>
      </div>
    </div>
    <!-- <div> -->
    <div class="container-fluid p-0">
      <div class="row p-0 m-0">
        <div
          class="col-md-3 col-sm-6 col-xs-6 col-6 col-gap"
          v-for="(product, index) in response.products"
          :key="index"
        >
          <div class="card card_wrapper border-0">
            <img
              v-show="product.plus_size"
              src="https://wforwomanonline.com/images/plus_size_new.png"
              class="puls_size_img"
              alt="..."
            />
            <img :src="product.image" class="card-img-top" alt="..." />
            <div class="card-body">
              <p class="card-text">
                {{ product.name }}
              </p>
              <p class="card-text">Rs. {{ product.price }}</p>
              <p class="card-text size_label">
                Size -
                {{
                  product.size
                    .replaceAll("[", "")
                    .replaceAll("]", "")
                    .replaceAll(",", " ")
                }}
              </p>
            </div>
          </div>
        </div>
        <div v-show="loading" class="spinner-border m-5" role="status">
          <span class="sr-only">Loading...</span>
        </div>
      </div>
    </div>
    <!-- </div> -->
  </div>
</template>

<script>
export default {
  name: "RightSide",
  props: ["response","loading"],
  data() {
    return {
      // response: [],
    };
  },
  methods: {},
};
</script>

<style scoped>
.size_label {
  visibility: hidden;
}
.card_wrapper:hover .size_label {
  visibility: visible;
}

.card_wrapper:hover {
  border: 1px solid #ededed !important;
}
.card_wrapper {
  position: relative;
  border: 1px solid transparent !important;
}
.puls_size_img {
  position: absolute;
  width: 40%;
  top: 15px;
  left: 0;
}
.card-body {
  padding: 10px;
}
.card-text {
  font-size: 14px !important;
  margin-bottom: 6px;
}
.col-gap {
  padding: 20px !important;
  padding: 0;
}
.container {
  margin: 0 !important;
  padding: 0;
  /* width: 100% !important; */
}
/* .card {
  padding-right: 10px;
} */
.right_side_wrapper {
  width: calc(100vw - 25%);

  /* background: red; */
  /* padding: 10px 0px 10px 20px; */
}
.total_item_wrapper {
  border: 1px solid #ededed;
  padding: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
  margin: 10px 20px 20px;
}
.total_item_wrapper p {
  margin: 0;
}
</style>