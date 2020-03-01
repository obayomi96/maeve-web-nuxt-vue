<template>
  <Layout>
    <main>
      <section class="hero_in hotels_detail">
        <div class="wrapper">
          <div class="container" v-bind="experience" >
            <h1 class="fadeInUvp"><span></span>{{experience.name}}</h1>
          </div>
          <span class="magnific-gallery">
            <a href="img/gallery/hotel_list_2.jpg" title="Photo title" data-effect="mfp-zoom-in"></a>
            <a href="img/gallery/hotel_list_3.jpg" title="Photo title" data-effect="mfp-zoom-in"></a>
          </span>
        </div>
      </section>
		  <!--/hero_in-->
      <div class="bg_color_1">
        <nav class="secondary_nav" :class="[sticky_horizontal ? 'sticky sticky_margin' : '']">
          <div class="container" style="display:flex;justify-content:space-between">
            <ul class="clearfix">
              <li>Description</li>
              <li>Reviews</li>
            </ul>
            <div class="btn book-btn">
              BOOK NOW
            </div>
          </div>
        </nav>
        <div class="container margin_60_35">
          <div class="row">
            <div class="col-lg-8">
              <section id="description">
                <h2>Description</h2>
                <p>{{experience.details}}</p>
                <div class="exp-img-layout">
                  <img alt="" src="../../img/layer-5.png">
                </div>
                <p>Cum et probo menandri. Officiis consulatu pro et, ne sea sale invidunt, sed ut sint <strong>blandit</strong> efficiendi. Atomorum explicari eu qui, est enim quaerendum te. Quo harum viris id. Per ne quando dolore evertitur, pro ad cibo commune.</p>
                <div class="row">
                  <div class="col-lg-6">
                    <ul class="bullets">
                      <li>Dolorem mediocritatem</li>
                      <li>Mea appareat</li>
                      <li>Prima causae</li>
                      <li>Singulis indoctum</li>
                    </ul>
                  </div>
                  <div class="col-lg-6">
                    <ul class="bullets">
                      <li>Timeam inimicus</li>
                      <li>Oportere democritum</li>
                      <li>Cetero inermis</li>
                      <li>Pertinacia eum</li>
                    </ul>
                  </div>
                </div>
                <!-- /row -->
                <hr>
                <h3>Location</h3>
                <div id="map" class="map map_single add_bottom_30">
                  <img alt="" src="../../img/test-map.png" />
                </div>
                <!-- End Map -->
              </section>
              <!-- /section -->
            
              <section id="reviews">
                <h2>Reviews</h2>
                <div class="reviews-container">
                  <div class="row">
                    <div class="col-lg-3">
                      <div id="review_summary">
                        <strong>8.5</strong>
                        <em>Superb</em>
                        <small>Based on 4 reviews</small>
                      </div>
                    </div>
                    <div class="col-lg-9">
                      <div class="row">
                        <div class="col-lg-10 col-9">
                          <div class="progress">
                            <div class="progress-bar" role="progressbar" style="width: 90%" aria-valuenow="90" aria-valuemin="0" aria-valuemax="100"></div>
                          </div>
                        </div>
                        <div class="col-lg-2 col-3"><small><strong>5 stars</strong></small></div>
                      </div>
                      <!-- /row -->
                      <div class="row">
                        <div class="col-lg-10 col-9">
                          <div class="progress">
                            <div class="progress-bar" role="progressbar" style="width: 95%" aria-valuenow="95" aria-valuemin="0" aria-valuemax="100"></div>
                          </div>
                        </div>
                        <div class="col-lg-2 col-3"><small><strong>4 stars</strong></small></div>
                      </div>
                      <!-- /row -->
                      <div class="row">
                        <div class="col-lg-10 col-9">
                          <div class="progress">
                            <div class="progress-bar" role="progressbar" style="width: 60%" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"></div>
                          </div>
                        </div>
                        <div class="col-lg-2 col-3"><small><strong>3 stars</strong></small></div>
                      </div>
                      <!-- /row -->
                      <div class="row">
                        <div class="col-lg-10 col-9">
                          <div class="progress">
                            <div class="progress-bar" role="progressbar" style="width: 20%" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100"></div>
                          </div>
                        </div>
                        <div class="col-lg-2 col-3"><small><strong>2 stars</strong></small></div>
                      </div>
                      <!-- /row -->
                      <div class="row">
                        <div class="col-lg-10 col-9">
                          <div class="progress">
                            <div class="progress-bar" role="progressbar" style="width: 0" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100"></div>
                          </div>
                        </div>
                        <div class="col-lg-2 col-3"><small><strong>1 stars</strong></small></div>
                      </div>
                      <!-- /row -->
                    </div>
                  </div>
                  <!-- /row -->
                </div>

                <hr>

                <div class="reviews-container">

                  <div class="review-box clearfix">
                    <figure class="rev-thumb"><img src="../../img/avatar1.jpg" alt="">
                    </figure>
                    <div class="rev-content">
                      <div class="rating">
                        <i class="icon_star voted"></i><i class="icon_star voted"></i><i class="icon_star voted"></i><i class="icon_star voted"></i><i class="icon_star"></i>
                      </div>
                      <div class="rev-info">
                        Admin – April 03, 2016:
                      </div>
                      <div class="rev-text">
                        <p>
                          Sed eget turpis a pede tempor malesuada. Vivamus quis mi at leo pulvinar hendrerit. Cum sociis natoque penatibus et magnis dis
                        </p>
                      </div>
                    </div>
                  </div>
                  <!-- /review-box -->
                  <div class="review-box clearfix">
                    <figure class="rev-thumb"><img src="../../img/avatar2.jpg" alt="">
                    </figure>
                    <div class="rev-content">
                      <div class="rating">
                        <i class="icon-star voted"></i><i class="icon_star voted"></i><i class="icon_star voted"></i><i class="icon_star voted"></i><i class="icon_star"></i>
                      </div>
                      <div class="rev-info">
                        Ahsan – April 01, 2016:
                      </div>
                      <div class="rev-text">
                        <p>
                          Sed eget turpis a pede tempor malesuada. Vivamus quis mi at leo pulvinar hendrerit. Cum sociis natoque penatibus et magnis dis
                        </p>
                      </div>
                    </div>
                  </div>
                  <!-- /review-box -->
                  <div class="review-box clearfix">
                    <figure class="rev-thumb"><img src="../../img/avatar3.jpg" alt="">
                    </figure>
                    <div class="rev-content">
                      <div class="rating">
                        <i class="icon-star voted"></i><i class="icon_star voted"></i><i class="icon_star voted"></i><i class="icon_star voted"></i><i class="icon_star"></i>
                      </div>
                      <div class="rev-info">
                        Sara – March 31, 2016:
                      </div>
                      <div class="rev-text">
                        <p>
                          Sed eget turpis a pede tempor malesuada. Vivamus quis mi at leo pulvinar hendrerit. Cum sociis natoque penatibus et magnis dis
                        </p>
                      </div>
                    </div>
                  </div>
                  <!-- /review-box -->
                </div>
                <!-- /review-container -->
              </section>
              <!-- /section -->
              <hr>

                <div class="add-review">
                  <h5>Leave a Review</h5>
                  <form>
                    <div class="row">
                      <div class="form-group col-md-6">
                        <label>Name and Lastname *</label>
                        <input type="text" name="name_review" id="name_review" placeholder="" class="form-control">
                      </div>
                      <div class="form-group col-md-6">
                        <label>Email *</label>
                        <input type="email" name="email_review" id="email_review" class="form-control">
                      </div>
                      <div class="form-group col-md-6">
                        <label>Rating </label>
                        <div class="custom-select-form">
                        <select name="rating_review" id="rating_review" class="wide">
                          <option value="1">1 (lowest)</option>
                          <option value="2">2</option>
                          <option value="3">3</option>
                          <option value="4">4</option>
                          <option value="5" selected>5 (medium)</option>
                          <option value="6">6</option>
                          <option value="7">7</option>
                          <option value="8">8</option>
                          <option value="9">9</option>
                          <option value="10">10 (highest)</option>
                        </select>
                        </div>
                      </div>
                      <div class="form-group col-md-12">
                        <label>Your Review</label>
                        <textarea name="review_text" id="review_text" class="form-control" style="height:130px;"></textarea>
                      </div>
                      <div class="form-group col-md-12 add_top_20">
                        <input type="submit" value="Submit" class="btn_1" id="submit-review">
                      </div>
                    </div>
                  </form>
                </div>
            </div>
            <!-- /col -->
            
            <aside class="col-lg-4" id="sidebar">
              <div :class="[sticky_form ? 'sticky_form' : '']">
                <div class="box_detail booking">
                  <div class="price">
                    <span>45$ <small>person</small></span>
                    <div class="score"><span>Good<em>350 Reviews</em></span><strong>7.0</strong></div>
                  </div>

                  <div class="form-group">
                    <input class="form-control" type="text" name="dates" placeholder="When..">
                    <i class="icon_calendar"></i>
                  </div>

                  <div class="panel-dropdown">
                    <a href="#">Guests <span class="qtyTotal">1</span></a>
                    <div class="panel-dropdown-content right">
                      <div class="qtyButtons">
                        <label>Adults</label>
                        <input type="text" name="qtyInput" value="1">
                      </div>
                      <div class="qtyButtons">
                        <label>Childrens</label>
                        <input type="text" name="qtyInput" value="0">
                      </div>
                    </div>
                  </div>

                  <div class="form-group clearfix">
                    <div class="custom-select-form">
                      <select class="wide">
                        <option>Room Type</option>	
                        <option>Single Room</option>
                        <option>Double Room</option>
                        <option>Suite Room</option>
                      </select>
                    </div>
                  </div>
                  <a href="cart-1.html" class=" add_top_30 btn_1 full-width purchase">Purchase</a>
                  <a href="wishlist.html" class="btn_1 full-width outline wishlist"><i class="icon_heart"></i> Add to wishlist</a>
                  <div class="text-center"><small>No money charged in this step</small></div>
                </div>
                <ul class="share-buttons">
                  <li><a class="fb-share" href="#0"><i class="social_facebook"></i> Share</a></li>
                  <li><a class="twitter-share" href="#0"><i class="social_twitter"></i> Tweet</a></li>
                  <li><a class="gplus-share" href="#0"><i class="social_googleplus"></i> Share</a></li>
                </ul>
              </div>
            </aside>
          </div>
          <!-- /row -->
        </div>
        <!-- /container -->
      </div>
		<!-- /bg_color_1 -->
	  </main>
  </Layout>
</template>


<script>
import Layout from '~/components/Layout'

export default {
  components: {
    Layout
  },
  data() {
    return {
      sticky_horizontal: false,
      sticky_form: false,
      experience: '',
    }
  },

async created() {
  try {
    const path = this.$route.params.id;
    const response = await this.$axios.get(`/experiences/${path}`)
    const { data } = response.data;
    if (response.status === 200) {
      this.experience = data;
    }
  } catch (err) {
      if (err) {
        // const { errors } = err.response.data;
        console.log('errer', err);
      }
    }
  },

  methods: {
    handleScroll: function() {
      if (window.scrollY > 500) {
        this.sticky_horizontal = true
         this.sticky_form = true
      } else {
        this.sticky_horizontal = false
         this.sticky_form = false
      }
    }
  },
  beforeMount () {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  }
}
</script>

<style>
.sticky_margin {
  margin-top: 72px;
  z-index: 200;
}
.sticky_form {
  position: sticky;
  top: 150px;
}
.exp-img-layout {
    width: inherit;
    height: 254px;
    object-fit: contain;
}
.exp-img-layout img {
    object-fit: cover;
    height: inherit;
    width: inherit;
}
.book-btn {
    margin-top: -7px;
    background-color: #c6153e;
    color: white;
}

@media (max-width: 768px) {
  .exp-img-layout img {
    object-fit: cover;
    height: inherit;
    width: 290px;
  }
}
@media (min-width: 769px) {
  .book-btn {
    display: none;
  }
}
@media (max-width: 320px) {
  .book-btn {
    font-size: 13px;
  }
}
</style>