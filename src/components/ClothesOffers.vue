<script></script>

<template>
  <div id="photos" class="col">
    <div class="card" style="width: 18rem">
      <div class="card-body">
        <h5 class="card-title">{{ sale.name }}</h5>
        <p class="card-text">
          {{ sale.price }}
        </p>
        <input @click="increase" type="button" class="btn btn-primary"  value="Buy" >
        <!-- <a href="#" class="btn btn-primary">BUY</a> -->
      </div>
      <img :src="sale.image"  class="card-img-bottom" alt="..." />

    </div>
  </div>
</template>

<script>
export default {
  props: {
    sale: {
      required: true,
      type: Object,
    },
    value:""

  },
//   props:["value"]

};
</script>

<style scoped>
#photos{
    margin-bottom: 50px;
}
.card-img-bottom{
    height: 58vh;
}
</style>
