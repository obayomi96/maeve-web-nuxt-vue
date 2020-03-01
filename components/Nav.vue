<template>
  <div class="top-nav">
    <div class="exp-btn-box">
      <div class="exp-btn">Experiences</div>
      <div class="vl"></div>
      <div class="exp-btn">
        <div>
          <img class="plane-icon" alt="" src="../img/icons/plane-icon.png"/>
        </div>
        Travel
      </div>
      <div class="vl"></div>
    </div>
    <div class="exp-btn-box">
      <div class="exp-btn right-float">
        <div>
          <img class="user-icon" alt="" src="../img/icons/user-icon.png"/>
        </div>
        My Account
      </div>
      <div class="exp-btn right-float">Help</div>
      <div class="">
        <div>
          <img class="cart-icon" alt="" src="../img/icons/supermarket-icon.png"/>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.top-nav {
  display: flex;
  justify-content: space-between;
  padding: 0px 31px 0px 0px;
  height: 40px;
  width: inherit;
  border-color: #e3e3e3;
  border-style: solid;
  border-width: thin;
  letter-spacing: normal;
  color: #6a6a6a;
}
.exp-btn-box {
  display: flex;
}
.exp-btn {
  display: flex;
  justify-content: center;
  width: 145px;
  height: 29px;
  padding-top: 6px;
  object-fit: contain;
  cursor: pointer;
}
.right-float {
  width: 105px;
}
.vl {
  width: 1px;
  background-color: #e3e3e3;
}
.exp-btn img {
    margin-right: 8px;
}
.plane-icon {
    height: 14px;
}
.user-icon, .cart-icon {
  height: 13px;
  margin-bottom: 3px;
}
.cart-icon {
  height: 13px;
  margin-bottom: -8px;
}

@media (max-width: 1024px) {
  .top-nav {
    display: none;
  }
}
@media (min-width: 1024px) {
  .top-nav {
    display: flex;
  }  
}
</style>