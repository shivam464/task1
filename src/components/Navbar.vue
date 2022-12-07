<template>
  <div class="header border-bottom">
    <nav class="navbar navbar-expand-lg navbar-light bg-white">
      <a class="navbar-brand" href="#"
        ><img
          class="logo"
          src="https://wforwomanonline.com/images/logo.png"
          alt=""
      /></a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item new-launch">
            <a class="nav-link" href="#"
              >NEW LAUNCH </a
            >
          </li>
          <li class="nav-item hover-color">
            <a class="nav-link" href="#">TOP WEAR</a>
          </li>
          
          <li class="nav-item hover-color">
            <a class="nav-link" href="#" tabindex="-1" aria-disabled="true"
              >BOTTOM WEAR</a
            >
          </li>
          <li class="nav-item hover-color">
            <a class="nav-link" href="#" tabindex="-1" aria-disabled="true"
              >COSMETICS</a
            >
          </li>
          <li class="nav-item hover-color">
            <a class="nav-link" href="#" tabindex="-1" aria-disabled="true"
              >FOOTWEAR</a
            >
          </li>
          <li class="nav-item hover-color">
            <a class="nav-link" href="#" tabindex="-1" aria-disabled="true"
              >WISHFUL</a
            >
          </li>
          <li class="nav-item hover-color">
            <a class="nav-link" href="#" tabindex="-1" aria-disabled="true"
              >PLUS SIZES</a
            >
          </li>
          <li class="nav-item hover-color">
            <a class="nav-link" href="#" tabindex="-1" aria-disabled="true"
              >STORIES BY W</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link sale" href="#" tabindex="-1" aria-disabled="true"
              >SALE</a
            >
          </li>
        </ul>
        <!-- <form class="form-inline my-2 my-lg-0"> -->
        <div class="search_login_wrapper">
          <div class="search_input_wrapper">
            <input
              class="form-control Search_input mr-sm-2"
              type="text"
              placeholder="Search"
              aria-label="Search"
            />
            <i class="fa-solid fa-magnifying-glass px-1"></i>
          </div>

          <div class="login_user">
            <i class="fa-regular fa-user"></i>
            <p>LOGIN</p>
          </div>
          <div class="login_user">
            <i class="fa-solid fa-bag-shopping"></i>
            <p>CART</p>
          </div>
        </div>
        <!-- </form> -->
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "NavBar",
  props: {
    // msg: String
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hover-color a:hover{
  color: #bf1616 !important;
}
.sale{
  color: #bf1616 !important;
}

.search_input_wrapper {
  border: 1px solid #ededed;
  display: flex;
  justify-content: center;
  margin-right: 10px;
  align-items: center;
}
.Search_input{
  border: none;
}
.Search_input:focus{
  outline: none;
   box-shadow: none;
}
.search_login_wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
.login_user {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 13px;
  margin-right: 15px;
  cursor: pointer;
}
.login_user p {
  margin-bottom: 0;
  margin-top: -15px;
  font-size: 10px;
}
.login_user i {
  font-size: 25px;
}

.logo {
  max-width: 93px;
}
.nav-link {
  font-size: 11px;
  font-weight: 700;
}
.header {
  position: fixed; /* Set the navbar to fixed position */
  z-index: 1; /*Add this*/
  width: 100%;
  /* height:50px; */
  text-align: center;
  vertical-align: middle;
  line-height: 50px;
  top: 0px;
}
.Search_input {
  position: relative;
  /* padding-right: 40px; */
}
.search_icon {
  position: absolute;
  right: 32px;
  font-size: 30px;
}
</style>
