<template>
  <div class="left_side_wrapper">
    <div class="a">
      <div class="left_label filter_heading">
        <p>FILTER</p>
      </div>

      <div class="container accordian_wrapper">
        <div id="accordion" class="accordion">
          <div class="card mb-0">
            <div v-for="(label, index) in response.filters" :key="index">
              <div
                class="card-header border-top border-bottom-0 collapsed"
                data-toggle="collapse"
                data-parent="#accordion"
                :href="'#flush-collapse' + index"
              >
                <a class="card-title"> {{ label.filter_lable }} </a>
              </div>
              <div
                :id="'flush-collapse' + index"
                class="card-body collapse "
                data-parent="#accordion"
              >
                <!-- <p>Anim pariatur cliche reprehenderit</p> -->
                <div
                  class="option_wrapper"
                  v-for="(option, index) in label.options"
                  :key="index"
                >
                  <div class="box"></div>
                  <p>{{option.value}} ({{option.total}})</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LeftSideBar",
  props: ["response"],
  data() {
    return {};
  },
};
</script>

<style scoped>
.a{
  border: 1px solid #ededed;
}
.left_side_wrapper {
  width: 25%;
  
  /* background: gray; */
}
.left_label {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px;
  cursor: pointer;
  font-size: 16px;
  /* border-bottom: 1px solid #ededed; */
}
.left_label:last-child {
  border-bottom: none;
}
.left_label p {
  margin: 0;
}
.filter_heading {
  cursor: auto;
  font-size: 16px;
  font-weight: 700;
}
.accordion .card-header:after {
  font-family: "FontAwesome";
  content: "\f078";
  float: right;
}
.accordion .card-header.collapsed:after {
  /* symbol for "collapsed" panels */
  content: "\f077";
}
.accordian_wrapper {
  padding: 0;
}
.card-header {
  /* border-bottom: none; */
  background: white;
}
/* .card-header ::after {
  border-bottom: none !important;
} */
.card {
  border: none;
}

.option_wrapper {
  display: flex;
  align-items: center;
  padding-bottom: 10px;
}
.option_wrapper p {
  margin-bottom: 0;
}
.box {
  width: 20px;
  height: 20px;
  background-color: #f1f1f1;
  margin-right: 10px;
}
.box:hover {
  background: #bf1616;
}
</style>
