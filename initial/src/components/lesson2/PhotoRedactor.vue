<template>
<div class="container">
  <h1>PhotoRedactor</h1>
<div class="flex">
  <div class="image-wrapper">
<img v-if="isCatVisible" :class="imgFilters" src="../../assets/images/cat.jpeg" alt="cat" :style="imgStyles">
<p v-else>The cat will be back soon</p>
  </div>
  </div>
  <div class="controls">
    <h2>Cat</h2>
    <button @click=" isCatVisible = ! isCatVisible">
      {{ isCatVisible? 'Hide' : 'Show' }}
    </button>
    <h2>Filters</h2>
   <div class="btn-group flex">
   <button type="button" @click="imgFilters.sepia = !imgFilters.sepia" :class="imgFilters.sepia? 'active' : ''">
    Sepia
   </button>
   <button type="button" @click="imgFilters.border = !imgFilters.border" :class="imgFilters.border? 'active' : ''">
    Border
   </button>
   <button type="button" @click="imgFilters.small = !imgFilters.small" :class="imgFilters.small? 'active' : ''">
    Small
   </button>
   <button type="button" @click="imgFilters.shadow = !imgFilters.shadow" :class="imgFilters.shadow? 'active' : ''">
    Shadow
   </button>
   </div>
<h2>Size</h2>
<div class="btn-group">
  <label>
      Width:{{ imgSizes.currentWidth }}
      <input
      type="range"
      :value="imgSizes.currentWidth"
      @input="imgSizes.currentWidth = $event.target.value"
      :min="imgSizes.minWidth"
      :max="imgSizes.maxWidth"
      >
    </label>
  </div>
  <h2>Turn</h2>
<div class="btn-group">
  <label>
      Rotate:{{ imgRotate.currentRotate }}
      <input
      type="range"
      :value="imgSizes.currentRotate"
      @input="imgRotate.currentRotate = $event.target.value"
      :min="imgRotate.minRotate"
      :max="imgRotate.maxRotate"
      >
    </label>
  </div>
</div>
</div>
</template>
<script>
export default {
  name: 'PhotoRedactor',
  data () {
    return {
      isCatVisible: true,
      imgFilters: {
        sepia: false,
        border: false,
        small: false
      },
      imgSizes: {
        maxWidth: 680,
        minWidth: 380,
        currentWidth: 380
      },
      imgRotate: {
        minRotate: 0,
        maxRotate: 360,
        currentRotate: 0
      }
    }
  },
  computed: {
    imgStyles () {
      return {
        width: `${this.imgSizes.currentWidth}px`,
        transform: `rotate(${this.imgRotate.currentRotate}deg)`
      }
    }
  }
}

</script>
<style lang="scss">

.container{
  margin-top: 40px;
}
.controls{
  margin-left: 20px;
}
.image-wrapper{
  background-color: antiquewhite;
  width:380px;
}
img {
  transition: 0.2s ease;
  &.sepia{
    filter:sepia(100%);
  }
  &.border{
  border: 5px dashed #464646;
  }
  &.small{
    width:240px;
  }
  &.shadow{
    box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.305);
  }
  button {
    margin-right: 10px;
    &.active {
      background-color: #dbdbdb;
    }
  }
  h2 {
    margin-bottom: 10px;
  }
  .btn-group {
    margin-bottom: 20px;
  }
  input[type="range"] {
    display: block;
  }
}
</style>
