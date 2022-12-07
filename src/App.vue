<template>
  <div>
    <NavBar />
    <div class="data_wrapper">
      <left-side-bar :response="response" />
      <right-side :response="response" :loading="loading" />
    </div>
  </div>
</template>

<script>
import LeftSideBar from "./components/LeftSideBar.vue";
import NavBar from "./components/Navbar.vue";
import RightSide from "./components/RightSide.vue";
// import './assets/main.css'

export default {
  name: "App",
  components: {
    NavBar,
    LeftSideBar,
    RightSide,
  },
  data() {
    return {
      response: [],
      limit: 15,
      loading: false,
    };
  },

  mounted() {
    this.getResponse(this.limit);
    this.getNextUser();
  },
  methods: {
    getNextUser() {
      window.onscroll = () => {
        const height = Math.trunc(
          document.documentElement.scrollTop + window.innerHeight
        );
        const offsetHeight = document.documentElement.offsetHeight;
        const checkvalue =
          height == offsetHeight ||
          height - 1 == offsetHeight ||
          height == offsetHeight - 1;
        if (checkvalue) {
          this.limit += 15;
          this.getResponse(this.limit);
        }
      };
    },
    async getResponse(limit) {
      this.loading = true;
      const resp = await fetch(
        `https://pim.wforwoman.com/pim/pimresponse.php/?service=category&store=1&url_key=top-wear-kurtas&page=1&count=${limit}&sort_by=&sort_dir=desc&filter=`
      ).then((res) => res.json());
      this.response = resp.result;
      this.loading = false;
      // console.log("res", this.response);
    },
  },
};
</script>

<style >
.abc {
  width: 100vw;
  height: 100vh;
  overflow-x: hidden;
  overflow-y: scroll;
  scroll-behavior: smooth;
}
.data_wrapper {
  display: flex;
  justify-content: center;
  width: 100%;
  padding: 10px 30px;
  margin-top: 6rem;
}
.body {
  margin: 0 !important;
  padding: 0 !important;
  box-sizing: border-box;
}
</style>
