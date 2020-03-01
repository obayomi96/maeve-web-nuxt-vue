<template>
  <div>
    <div class="filter-search">
      <div class="search-bar search-bar-filter">
        <input class="search-filter-input" placeholder="Terms..."/>
        <img class="magnifying-glass" alt="" src="../img/icons/magnifying-glass-icon.png" />
      </div>
      <button class="btn">Search</button>
    </div>
    <div class="filter-web">
      <div class="filter-web-header">
        <div>Filters</div>
        <div>
          <img alt="" src="https://cdn1.iconfinder.com/data/icons/web-ui-2/16/UI_Icons_Outline-25-512.png" />
        </div>
      </div>
      <div class="filter-web-tag">
        <div class="filter-web-tag-header">Restaurant</div>
        <div class="filter-web-tag-options">
          <input type="checkbox" name="option1" value="alll">All (9)<br>
          <input type="checkbox" name="option2" value="bars">Bars (2)<br>
          <input type="checkbox" name="option3" value="coffee" checked>Coffee Bars (3)<br><br>
        </div>
      </div>
      <div class="filter-web-tag">
        <div class="filter-web-tag-header">District</div>
        <div class="filter-web-tag-options">
          <input type="checkbox" name="option1" value="alll">All (9)<br>
          <input type="checkbox" name="option2" value="bars">Bars (2)<br>
          <input type="checkbox" name="option3" value="coffee" checked>Coffee Bars (3)<br><br>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.filter-web-tag-header {
  font-weight: bold;
  margin-bottom: 10px
}
.filter-web-tag {
  height: fit-content;
  padding: 10px 0px;
  border-top-style: solid;
  border-top-color: #e3e3e3;
  border-top-width: thin;
  font-size: 12px;
}
.filter-web-header img {
    height: 17px;
    object-fit: contain;
}
.filter-web-header {
  height: 40px;
  width: inherit;
  font-weight: bold;
  display: flex;
  justify-content: space-between;
}
.filter-web {
  padding: 10px 10px;
  height: fit-content;
  width: inherit;
  border-style: solid;
  border-color: #e3e3e3;
  border-width: thin;
}
.search-filter-input {
  width: 235px;
}
.filter-search {
  font-weight: bold;
  font-size: 14px;
  margin-bottom: 30px;
}
.search-bar-filter {
  margin: 0px;
  width: inherit;
  margin-bottom: 10px;
} 
button {
  width: -webkit-fill-available;
  background-color: #fc5b62;
  color: white;
}
</style>