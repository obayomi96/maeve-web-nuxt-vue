<template>
  <Layout >
    <main>
      <div class="listing-banner-container">
        <div class="listing-banner container">
          <div class="advert-board-listing">
            <img alt src="../../img/advert-board.png" />
          </div>Search Result for "Food & Drink"
          <br />
          <span class="result-listing">
            <i>Showing 100 results</i>
          </span>
        </div>
      </div>
      <div class="filters_listing" :class="[sticky_horizontal ? 'sticky sticky_margin' : '']">
        <div class="container">
          <ul class="clearfix">
            <li>
              <div class="switch-field">
                <input
                  type="radio"
                  id="all"
                  name="listing_filter"
                  value="all"
                  checked
                  data-filter="*"
                  class="selected"
                />
                <label for="all">All</label>
                <input
                  type="radio"
                  id="popular"
                  name="listing_filter"
                  value="popular"
                  data-filter=".popular"
                />
                <label for="popular">Popular</label>
                <input
                  type="radio"
                  id="latest"
                  name="listing_filter"
                  value="latest"
                  data-filter=".latest"
                />
                <label for="latest">Latest</label>
              </div>
            </li>
            <li>
              <div class="layout_view">
                <a href="#0" class="active">
                  <i class="icon-th"></i>
                </a>
                <a href="restaurants-list-isotope.html">
                  <i class="icon-th-list"></i>
                </a>
              </div>
            </li>
            <!-- <li>
              <a class="btn_map" data-toggle="collapse" href="#collapseMap" aria-expanded="false" aria-controls="collapseMap" data-text-swap="Hide map" data-text-original="View on map">View on map</a>
            </li>-->
          </ul>
        </div>
        <!-- /container -->
      </div>
      <div class="collapse" id="collapseMap">
        <div id="map" class="map"></div>
      </div>
      <div class="container margin_60_35">
        <div class="row">
          <aside class="col-lg-3" id="sidebar">
            <!-- <div class="custom-search-input-2 inner-2">
              <div class="form-group">
                <input class="form-control" type="text" placeholder="Terms...">
                <i class="icon_search"></i>
              </div>
						  <input type="submit" class="btn_search" value="Search">
            </div>-->
            <div id="filters_col">
              <a
                data-toggle="collapse"
                @click="handleShow"
                aria-expanded="false"
                aria-controls="collapseFilters"
                id="filters_col_bt"
              >Filters</a>
              <div class="collapse" :class="[show ? 'show' : '']" id="collapseFilters">
                <div class="filter_type">
                  <h6>Category</h6>
                  <ul>
                    <li>
                      <label>
                        <input type="checkbox" class="icheck" checked />All
                        <small>(945)</small>
                      </label>
                    </li>
                    <li>
                      <label>
                        <input type="checkbox" class="icheck" />Restaurants
                        <small>(45)</small>
                      </label>
                    </li>
                    <li>
                      <label>
                        <input type="checkbox" class="icheck" />Bars
                        <small>(30)</small>
                      </label>
                    </li>
                    <li>
                      <label>
                        <input type="checkbox" class="icheck" />Coffe Bars
                        <small>(25)</small>
                      </label>
                    </li>
                  </ul>
                </div>
                <div class="filter_type">
                  <h6>Rating</h6>
                  <ul>
                    <li>
                      <label>
                        <input type="checkbox" class="icheck" />Superb 9+
                        <small>(25)</small>
                      </label>
                    </li>
                    <li>
                      <label>
                        <input type="checkbox" class="icheck" />Very Good 8+
                        <small>(26)</small>
                      </label>
                    </li>
                    <li>
                      <label>
                        <input type="checkbox" class="icheck" />Good 7+
                        <small>(25)</small>
                      </label>
                    </li>
                    <li>
                      <label>
                        <input type="checkbox" class="icheck" />Pleasant 6+
                        <small>(12)</small>
                      </label>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </aside>
          <!-- /aside -->

          <div class="col-lg-9">
            <div class="isotope-wrapper">
              <div class="row">
                <BoxList />
                <BoxList />
                <BoxList />
                <BoxList />
                <BoxList />
                <BoxList />
                <!-- /box_grid -->
              </div>
              <!-- /row -->
            </div>
            <!-- /isotope-wrapper -->

            <p class="text-center">
              <a href="#0" class="btn_1 rounded add_top_30">Load more</a>
            </p>
          </div>
          <!-- /col -->
        </div>
      </div>
      <div class="bg_color_1">
        <div class="container margin_60_35">
          <div class="row">
            <div class="col-md-4">
              <a href="#0" class="boxed_list">
                <i class="pe-7s-help2"></i>
                <h4>Need Help? Contact us</h4>
                <p>Cum appareat maiestatis interpretaris et, et sit.</p>
              </a>
            </div>
            <div class="col-md-4">
              <a href="#0" class="boxed_list">
                <i class="pe-7s-wallet"></i>
                <h4>Payments and Refunds</h4>
                <p>Qui ea nemore eruditi, magna prima possit eu mei.</p>
              </a>
            </div>
            <div class="col-md-4">
              <a href="#0" class="boxed_list">
                <i class="pe-7s-note2"></i>
                <h4>Quality Standards</h4>
                <p>Hinc vituperata sed ut, pro laudem nonumes ex.</p>
              </a>
            </div>
          </div>
        </div>
      </div>
    </main>
  </Layout>
</template>

<script>
import Layout from "~/components/Layout";
import BoxList from "~/components/BoxList";
import Filters from "~/components/Filters";

export default {
  components: {
    Layout,
    BoxList,
    Filters
  },
  data() {
    return {
      show: true,
      sticky_horizontal: false,
      searchResult: []
    };
  },
  async created() {
    const config = {
      headers: {
        Accepts: "application/json"
      }
    };

    try {
      const response = await this.$axios.get(
        "/experiences/search?name=picnic",
        config
      );

      const { data } = response.data;

      console.log('res data', data);

      this.searchResult = data;
      console.log('res result', this.searchResult);
    } catch (err) {
      console.log("search err", err);
    }
  },
  methods: {
    async searchText(text) {
      const config = {
      headers: {
        Accepts: "application/json"
      }
    };

    try {
      const response = await this.$axios.get(
        `/experiences/search?name=${text}`,
        config
      );

      const { data } = response.data;

      console.log('res data', data);

      this.searchResult = data;
      console.log('res result', this.searchResult);
    } catch (err) {
      console.log("search err", err);
    }
    },
    handleShow() {
      this.show = !this.show;
    },
    handleScroll: function() {
      if (window.scrollY > 150) {
        this.sticky_horizontal = true;
      } else {
        this.sticky_horizontal = false;
      }
    }
  },
  beforeMount() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  }
};
</script>

<style>
.sticky_margin {
  margin-top: 72px;
}
.listing-filters {
  width: 30%;
  padding-right: 40px;
}
.listing-content {
  display: flex;
  flex-wrap: wrap;
  width: 70%;
}
.listing-main-content {
  display: flex;
  height: fit-content;
  width: 68%;
  margin-top: 80px;
}
.listing-main-content {
  height: inherit;
}
.listing-banner-container {
  height: fit-content;
  width: inherit;
  background-color: white;
  display: flex;
  justify-content: center;
}
.listing-banner {
  height: inherit;
  font-size: 30px;
  font-family: Open Sans;
  color: #6a6a6a;
  font-weight: 300;
  margin-bottom: 30px;
}
.result-listing {
  height: inherit;
  font-size: 14px;
  font-family: Open Sans;
  color: #6a6a6a;
  font-weight: 300;
  margin-bottom: 30px;
}
.advert-board-listing {
  height: 102px;
  width: -webkit-fill-available;
  margin-bottom: 15px;
}
.advert-board-listing img {
  height: inherit;
  width: inherit;
  object-fit: fill;
}
</style>